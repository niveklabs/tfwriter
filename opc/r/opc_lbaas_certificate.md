# opc_lbaas_certificate

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_lbaas_certificate" {
  source = "./modules/opc/r/opc_lbaas_certificate"

  # certificate_body - (required) is a type of string
  certificate_body = null
  # certificate_chain - (optional) is a type of string
  certificate_chain = null
  # name - (required) is a type of string
  name = null
  # private_key - (optional) is a type of string
  private_key = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "certificate_body" {
  description = "(required)"
  type        = string
}

variable "certificate_chain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "private_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "opc_lbaas_certificate" "this" {
  certificate_body  = var.certificate_body
  certificate_chain = var.certificate_chain
  name              = var.name
  private_key       = var.private_key
  type              = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_lbaas_certificate.this.id
}

output "state" {
  description = "returns a string"
  value       = opc_lbaas_certificate.this.state
}

output "uri" {
  description = "returns a string"
  value       = opc_lbaas_certificate.this.uri
}

output "this" {
  value = opc_lbaas_certificate.this
}
```

[top](#index)