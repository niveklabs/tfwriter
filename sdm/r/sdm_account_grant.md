# sdm_account_grant

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
module "sdm_account_grant" {
  source = "./modules/sdm/r/sdm_account_grant"

  # account_id - (required) is a type of string
  account_id = null
  # resource_id - (required) is a type of string
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
  description = "(required) - The id of the attached role of this AccountGrant."
  type        = string
}

variable "resource_id" {
  description = "(required) - The id of the composite role of this AccountGrant."
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
resource "sdm_account_grant" "this" {
  # account_id - (required) is a type of string
  account_id = var.account_id
  # resource_id - (required) is a type of string
  resource_id = var.resource_id

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
output "id" {
  description = "returns a string"
  value       = sdm_account_grant.this.id
}

output "this" {
  value = sdm_account_grant.this
}
```

[top](#index)