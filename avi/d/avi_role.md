# avi_role

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
module "avi_role" {
  source = "./modules/avi/d/avi_role"

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
data "avi_role" "this" {
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
output "id" {
  description = "returns a string"
  value       = data.avi_role.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_role.this.name
}

output "privileges" {
  description = "returns a list of object"
  value       = data.avi_role.this.privileges
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_role.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_role.this.uuid
}

output "this" {
  value = avi_role.this
}
```

[top](#index)