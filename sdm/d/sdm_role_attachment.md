# sdm_role_attachment

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
module "sdm_role_attachment" {
  source = "./modules/sdm/d/sdm_role_attachment"

  # attached_role_id - (optional) is a type of string
  attached_role_id = null
  # composite_role_id - (optional) is a type of string
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
  description = "(optional) - The id of the attached role of this RoleAttachment."
  type        = string
  default     = null
}

variable "composite_role_id" {
  description = "(optional) - The id of the composite role of this RoleAttachment."
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
data "sdm_role_attachment" "this" {
  # attached_role_id - (optional) is a type of string
  attached_role_id = var.attached_role_id
  # composite_role_id - (optional) is a type of string
  composite_role_id = var.composite_role_id

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
  value       = data.sdm_role_attachment.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.sdm_role_attachment.this.ids
}

output "role_attachments" {
  description = "returns a list of object"
  value       = data.sdm_role_attachment.this.role_attachments
}

output "this" {
  value = sdm_role_attachment.this
}
```

[top](#index)