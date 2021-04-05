# sdm_role_attachment

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
module "sdm_role_attachment" {
  source = "./modules/sdm/r/sdm_role_attachment"

  # attached_role_id - (required) is a type of string
  attached_role_id = null
  # composite_role_id - (required) is a type of string
  composite_role_id = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "attached_role_id" {
  description = "(required) - The id of the attached role of this RoleAttachment."
  type        = string
}

variable "composite_role_id" {
  description = "(required) - The id of the composite role of this RoleAttachment."
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
resource "sdm_role_attachment" "this" {
  attached_role_id  = var.attached_role_id
  composite_role_id = var.composite_role_id

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
  value       = sdm_role_attachment.this.id
}

output "this" {
  value = sdm_role_attachment.this
}
```

[top](#index)