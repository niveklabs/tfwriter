# avi_customipamdnsprofile

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
module "avi_customipamdnsprofile" {
  source = "./modules/avi/r/avi_customipamdnsprofile"

  # name - (optional) is a type of string
  name = null
  # script_uri - (optional) is a type of string
  script_uri = null
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "script_uri" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "avi_customipamdnsprofile" "this" {
  # name - (optional) is a type of string
  name = var.name
  # script_uri - (optional) is a type of string
  script_uri = var.script_uri
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "script_params" {
    for_each = var.script_params
    content {
      # is_dynamic - (optional) is a type of bool
      is_dynamic = script_params.value["is_dynamic"]
      # is_sensitive - (optional) is a type of bool
      is_sensitive = script_params.value["is_sensitive"]
      # name - (required) is a type of string
      name = script_params.value["name"]
      # value - (optional) is a type of string
      value = script_params.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = avi_customipamdnsprofile.this.id
}

output "name" {
  description = "returns a string"
  value       = avi_customipamdnsprofile.this.name
}

output "script_uri" {
  description = "returns a string"
  value       = avi_customipamdnsprofile.this.script_uri
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_customipamdnsprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_customipamdnsprofile.this.uuid
}

output "this" {
  value = avi_customipamdnsprofile.this
}
```

[top](#index)