# ecl_network_fic_gateway_v2

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_network_fic_gateway_v2" {
  source = "./modules/ecl/d/ecl_network_fic_gateway_v2"

  # description - (optional) is a type of string
  description = null
  # fic_gateway_id - (optional) is a type of string
  fic_gateway_id = null
  # fic_service_id - (optional) is a type of string
  fic_service_id = null
  # name - (optional) is a type of string
  name = null
  # qos_option_id - (optional) is a type of string
  qos_option_id = null
  # status - (optional) is a type of string
  status = null
  # tenant_id - (optional) is a type of string
  tenant_id = null
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

variable "fic_gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fic_service_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "qos_option_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ecl_network_fic_gateway_v2" "this" {
  description    = var.description
  fic_gateway_id = var.fic_gateway_id
  fic_service_id = var.fic_service_id
  name           = var.name
  qos_option_id  = var.qos_option_id
  status         = var.status
  tenant_id      = var.tenant_id
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.ecl_network_fic_gateway_v2.this.description
}

output "fic_gateway_id" {
  description = "returns a string"
  value       = data.ecl_network_fic_gateway_v2.this.fic_gateway_id
}

output "fic_service_id" {
  description = "returns a string"
  value       = data.ecl_network_fic_gateway_v2.this.fic_service_id
}

output "id" {
  description = "returns a string"
  value       = data.ecl_network_fic_gateway_v2.this.id
}

output "name" {
  description = "returns a string"
  value       = data.ecl_network_fic_gateway_v2.this.name
}

output "qos_option_id" {
  description = "returns a string"
  value       = data.ecl_network_fic_gateway_v2.this.qos_option_id
}

output "status" {
  description = "returns a string"
  value       = data.ecl_network_fic_gateway_v2.this.status
}

output "tenant_id" {
  description = "returns a string"
  value       = data.ecl_network_fic_gateway_v2.this.tenant_id
}

output "this" {
  value = ecl_network_fic_gateway_v2.this
}
```

[top](#index)