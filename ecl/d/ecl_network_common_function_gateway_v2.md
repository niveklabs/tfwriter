# ecl_network_common_function_gateway_v2

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
module "ecl_network_common_function_gateway_v2" {
  source = "./modules/ecl/d/ecl_network_common_function_gateway_v2"

  # common_function_pool_id - (optional) is a type of string
  common_function_pool_id = null
  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # network_id - (optional) is a type of string
  network_id = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # tenant_id - (optional) is a type of string
  tenant_id = null
}
```

[top](#index)

### Variables

```terraform
variable "common_function_pool_id" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "network_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_id" {
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
data "ecl_network_common_function_gateway_v2" "this" {
  common_function_pool_id = var.common_function_pool_id
  description             = var.description
  name                    = var.name
  network_id              = var.network_id
  subnet_id               = var.subnet_id
  tenant_id               = var.tenant_id
}
```

[top](#index)

### Outputs

```terraform
output "common_function_pool_id" {
  description = "returns a string"
  value       = data.ecl_network_common_function_gateway_v2.this.common_function_pool_id
}

output "description" {
  description = "returns a string"
  value       = data.ecl_network_common_function_gateway_v2.this.description
}

output "id" {
  description = "returns a string"
  value       = data.ecl_network_common_function_gateway_v2.this.id
}

output "name" {
  description = "returns a string"
  value       = data.ecl_network_common_function_gateway_v2.this.name
}

output "network_id" {
  description = "returns a string"
  value       = data.ecl_network_common_function_gateway_v2.this.network_id
}

output "subnet_id" {
  description = "returns a string"
  value       = data.ecl_network_common_function_gateway_v2.this.subnet_id
}

output "tenant_id" {
  description = "returns a string"
  value       = data.ecl_network_common_function_gateway_v2.this.tenant_id
}

output "this" {
  value = ecl_network_common_function_gateway_v2.this
}
```

[top](#index)