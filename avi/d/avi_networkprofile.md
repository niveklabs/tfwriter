# avi_networkprofile

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
module "avi_networkprofile" {
  source = "./modules/avi/d/avi_networkprofile"

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
data "avi_networkprofile" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "connection_mirror" {
  description = "returns a bool"
  value       = data.avi_networkprofile.this.connection_mirror
}

output "description" {
  description = "returns a string"
  value       = data.avi_networkprofile.this.description
}

output "id" {
  description = "returns a string"
  value       = data.avi_networkprofile.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_networkprofile.this.name
}

output "profile" {
  description = "returns a set of object"
  value       = data.avi_networkprofile.this.profile
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_networkprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_networkprofile.this.uuid
}

output "this" {
  value = avi_networkprofile.this
}
```

[top](#index)