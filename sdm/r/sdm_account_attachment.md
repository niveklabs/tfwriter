# sdm_account_attachment

[back](../sdm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/sdm/r/sdm_account_attachment"

  # account_id - (required) is a type of string
  account_id = null
  # role_id - (required) is a type of string
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
  description = "(required) - The id of the account of this AccountAttachment."
  type        = string
}

variable "role_id" {
  description = "(required) - The id of the attached role of this AccountAttachment."
  type        = string
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

### Resource

```terraform
resource "sdm_account_attachment" "this" {
  account_id = var.account_id
  role_id    = var.role_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sdm_account_attachment.this.id
}

output "this" {
  value = sdm_account_attachment.this
}
```

[top](#index)