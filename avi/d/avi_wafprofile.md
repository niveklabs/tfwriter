# avi_wafprofile

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "avi_wafprofile" {
  source = "./modules/avi/d/avi_wafprofile"

  # name - (optional) is a type of string
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
variable "name" {
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
```

[top](#index)

### Datasource

```terraform
data "avi_wafprofile" "this" {
  # name - (optional) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "config" {
  description = "returns a set of object"
  value       = data.avi_wafprofile.this.config
}

output "description" {
  description = "returns a string"
  value       = data.avi_wafprofile.this.description
}

output "files" {
  description = "returns a list of object"
  value       = data.avi_wafprofile.this.files
}

output "id" {
  description = "returns a string"
  value       = data.avi_wafprofile.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_wafprofile.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_wafprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_wafprofile.this.uuid
}

output "this" {
  value = avi_wafprofile.this
}
```

[top](#index)