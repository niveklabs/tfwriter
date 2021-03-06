# avi_pingaccessagent

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
module "avi_pingaccessagent" {
  source = "./modules/avi/d/avi_pingaccessagent"

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
data "avi_pingaccessagent" "this" {
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
output "description" {
  description = "returns a string"
  value       = data.avi_pingaccessagent.this.description
}

output "id" {
  description = "returns a string"
  value       = data.avi_pingaccessagent.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_pingaccessagent.this.name
}

output "pingaccess_pool_ref" {
  description = "returns a string"
  value       = data.avi_pingaccessagent.this.pingaccess_pool_ref
}

output "primary_server" {
  description = "returns a set of object"
  value       = data.avi_pingaccessagent.this.primary_server
}

output "properties_file_data" {
  description = "returns a string"
  value       = data.avi_pingaccessagent.this.properties_file_data
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_pingaccessagent.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_pingaccessagent.this.uuid
}

output "this" {
  value = avi_pingaccessagent.this
}
```

[top](#index)