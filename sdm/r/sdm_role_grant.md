# sdm_role_grant

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
module "sdm_role_grant" {
  source = "./modules/sdm/r/sdm_role_grant"

  # resource_id - (required) is a type of string
  resource_id = null
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
variable "resource_id" {
  description = "(required) - The id of the resource of this RoleGrant."
  type        = string
}

variable "role_id" {
  description = "(required) - The id of the attached role of this RoleGrant."
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
resource "sdm_role_grant" "this" {
  resource_id = var.resource_id
  role_id     = var.role_id

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
  value       = sdm_role_grant.this.id
}

output "this" {
  value = sdm_role_grant.this
}
```

[top](#index)