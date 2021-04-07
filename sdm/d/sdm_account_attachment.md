# sdm_account_attachment

[back](../sdm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sdm = ">= 1.0.19"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sdm_account_attachment" {
  source = "./modules/sdm/d/sdm_account_attachment"

  # account_id - (optional) is a type of string
  account_id = null
  # role_id - (optional) is a type of string
  role_id = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional) - The id of the account of this AccountAttachment."
  type        = string
  default     = null
}

variable "role_id" {
  description = "(optional) - The id of the attached role of this AccountAttachment."
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "sdm_account_attachment" "this" {
  # account_id - (optional) is a type of string
  account_id = var.account_id
  # role_id - (optional) is a type of string
  role_id = var.role_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # default - (optional) is a type of string
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "account_attachments" {
  description = "returns a list of object"
  value       = data.sdm_account_attachment.this.account_attachments
}

output "id" {
  description = "returns a string"
  value       = data.sdm_account_attachment.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.sdm_account_attachment.this.ids
}

output "this" {
  value = sdm_account_attachment.this
}
```

[top](#index)