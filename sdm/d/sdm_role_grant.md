# sdm_role_grant

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
module "sdm_role_grant" {
  source = "./modules/sdm/d/sdm_role_grant"

  # resource_id - (optional) is a type of string
  resource_id = null
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
variable "resource_id" {
  description = "(optional) - The id of the resource of this RoleGrant."
  type        = string
  default     = null
}

variable "role_id" {
  description = "(optional) - The id of the attached role of this RoleGrant."
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
data "sdm_role_grant" "this" {
  # resource_id - (optional) is a type of string
  resource_id = var.resource_id
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
output "id" {
  description = "returns a string"
  value       = data.sdm_role_grant.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.sdm_role_grant.this.ids
}

output "role_grants" {
  description = "returns a list of object"
  value       = data.sdm_role_grant.this.role_grants
}

output "this" {
  value = sdm_role_grant.this
}
```

[top](#index)