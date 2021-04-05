# sdm_account_grant

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
module "sdm_account_grant" {
  source = "./modules/sdm/d/sdm_account_grant"

  # account_id - (optional) is a type of string
  account_id = null
  # resource_id - (optional) is a type of string
  resource_id = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional) - The id of the attached role of this AccountGrant."
  type        = string
  default     = null
}

variable "resource_id" {
  description = "(optional) - The id of the composite role of this AccountGrant."
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
data "sdm_account_grant" "this" {
  account_id  = var.account_id
  resource_id = var.resource_id

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
output "account_grants" {
  description = "returns a list of object"
  value       = data.sdm_account_grant.this.account_grants
}

output "id" {
  description = "returns a string"
  value       = data.sdm_account_grant.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.sdm_account_grant.this.ids
}

output "this" {
  value = sdm_account_grant.this
}
```

[top](#index)