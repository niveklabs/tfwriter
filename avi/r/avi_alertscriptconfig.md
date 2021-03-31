# avi_alertscriptconfig

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
module "avi_alertscriptconfig" {
  source = "./modules/avi/r/avi_alertscriptconfig"

  # action_script - (optional) is a type of string
  action_script = null
  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "action_script" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
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
```

[top](#index)

### Resource

```terraform
resource "avi_alertscriptconfig" "this" {
  action_script = var.action_script
  name          = var.name
  tenant_ref    = var.tenant_ref
  uuid          = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "action_script" {
  description = "returns a string"
  value       = avi_alertscriptconfig.this.action_script
}

output "id" {
  description = "returns a string"
  value       = avi_alertscriptconfig.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_alertscriptconfig.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_alertscriptconfig.this.uuid
}

output "this" {
  value = avi_alertscriptconfig.this
}
```

[top](#index)