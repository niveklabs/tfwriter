# avi_protocolparser

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
module "avi_protocolparser" {
  source = "./modules/avi/r/avi_protocolparser"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # parser_code - (optional) is a type of string
  parser_code = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parser_code" {
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

### Resource

```terraform
resource "avi_protocolparser" "this" {
  description = var.description
  name        = var.name
  parser_code = var.parser_code
  tenant_ref  = var.tenant_ref
  uuid        = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = avi_protocolparser.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_protocolparser.this.id
}

output "name" {
  description = "returns a string"
  value       = avi_protocolparser.this.name
}

output "parser_code" {
  description = "returns a string"
  value       = avi_protocolparser.this.parser_code
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_protocolparser.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_protocolparser.this.uuid
}

output "this" {
  value = avi_protocolparser.this
}
```

[top](#index)