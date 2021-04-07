# avi_vsdatascriptset

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
module "avi_vsdatascriptset" {
  source = "./modules/avi/d/avi_vsdatascriptset"

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
data "avi_vsdatascriptset" "this" {
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
output "created_by" {
  description = "returns a string"
  value       = data.avi_vsdatascriptset.this.created_by
}

output "datascript" {
  description = "returns a list of object"
  value       = data.avi_vsdatascriptset.this.datascript
}

output "description" {
  description = "returns a string"
  value       = data.avi_vsdatascriptset.this.description
}

output "id" {
  description = "returns a string"
  value       = data.avi_vsdatascriptset.this.id
}

output "ipgroup_refs" {
  description = "returns a list of string"
  value       = data.avi_vsdatascriptset.this.ipgroup_refs
}

output "name" {
  description = "returns a string"
  value       = data.avi_vsdatascriptset.this.name
}

output "pool_group_refs" {
  description = "returns a list of string"
  value       = data.avi_vsdatascriptset.this.pool_group_refs
}

output "pool_refs" {
  description = "returns a list of string"
  value       = data.avi_vsdatascriptset.this.pool_refs
}

output "protocol_parser_refs" {
  description = "returns a list of string"
  value       = data.avi_vsdatascriptset.this.protocol_parser_refs
}

output "rate_limiters" {
  description = "returns a list of object"
  value       = data.avi_vsdatascriptset.this.rate_limiters
}

output "string_group_refs" {
  description = "returns a list of string"
  value       = data.avi_vsdatascriptset.this.string_group_refs
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_vsdatascriptset.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_vsdatascriptset.this.uuid
}

output "this" {
  value = avi_vsdatascriptset.this
}
```

[top](#index)