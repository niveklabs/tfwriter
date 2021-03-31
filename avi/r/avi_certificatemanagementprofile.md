# avi_certificatemanagementprofile

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_certificatemanagementprofile" {
  source = "./modules/avi/r/avi_certificatemanagementprofile"

  # name - (required) is a type of string
  name = null
  # script_path - (required) is a type of string
  script_path = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  script_params = [{
    is_dynamic   = null
    is_sensitive = null
    name         = null
    value        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "script_path" {
  description = "(required)"
  type        = string
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "script_params" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      is_dynamic   = bool
      is_sensitive = bool
      name         = string
      value        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_certificatemanagementprofile" "this" {
  name        = var.name
  script_path = var.script_path
  tenant_ref  = var.tenant_ref
  uuid        = var.uuid

  dynamic "script_params" {
    for_each = var.script_params
    content {
      is_dynamic   = script_params.value["is_dynamic"]
      is_sensitive = script_params.value["is_sensitive"]
      name         = script_params.value["name"]
      value        = script_params.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = avi_certificatemanagementprofile.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_certificatemanagementprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_certificatemanagementprofile.this.uuid
}

output "this" {
  value = avi_certificatemanagementprofile.this
}
```

[top](#index)