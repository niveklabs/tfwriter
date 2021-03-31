# avi_gslbgeodbprofile

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
module "avi_gslbgeodbprofile" {
  source = "./modules/avi/d/avi_gslbgeodbprofile"

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
data "avi_gslbgeodbprofile" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.avi_gslbgeodbprofile.this.description
}

output "entries" {
  description = "returns a list of object"
  value       = data.avi_gslbgeodbprofile.this.entries
}

output "id" {
  description = "returns a string"
  value       = data.avi_gslbgeodbprofile.this.id
}

output "is_federated" {
  description = "returns a bool"
  value       = data.avi_gslbgeodbprofile.this.is_federated
}

output "name" {
  description = "returns a string"
  value       = data.avi_gslbgeodbprofile.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_gslbgeodbprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_gslbgeodbprofile.this.uuid
}

output "this" {
  value = avi_gslbgeodbprofile.this
}
```

[top](#index)