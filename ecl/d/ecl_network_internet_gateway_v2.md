# ecl_network_internet_gateway_v2

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
    ecl = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_network_internet_gateway_v2" {
  source = "./modules/ecl/d/ecl_network_internet_gateway_v2"

  # description - (optional) is a type of string
  description = null
  # internet_gateway_id - (optional) is a type of string
  internet_gateway_id = null
  # internet_service_id - (optional) is a type of string
  internet_service_id = null
  # name - (optional) is a type of string
  name = null
  # qos_option_id - (optional) is a type of string
  qos_option_id = null
  # region - (optional) is a type of string
  region = null
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

variable "internet_gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_service_id" {
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

variable "region" {
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
data "ecl_network_internet_gateway_v2" "this" {
  description         = var.description
  internet_gateway_id = var.internet_gateway_id
  internet_service_id = var.internet_service_id
  name                = var.name
  qos_option_id       = var.qos_option_id
  region              = var.region
  status              = var.status
  tenant_id           = var.tenant_id
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.ecl_network_internet_gateway_v2.this.description
}

output "id" {
  description = "returns a string"
  value       = data.ecl_network_internet_gateway_v2.this.id
}

output "internet_gateway_id" {
  description = "returns a string"
  value       = data.ecl_network_internet_gateway_v2.this.internet_gateway_id
}

output "internet_service_id" {
  description = "returns a string"
  value       = data.ecl_network_internet_gateway_v2.this.internet_service_id
}

output "name" {
  description = "returns a string"
  value       = data.ecl_network_internet_gateway_v2.this.name
}

output "qos_option_id" {
  description = "returns a string"
  value       = data.ecl_network_internet_gateway_v2.this.qos_option_id
}

output "region" {
  description = "returns a string"
  value       = data.ecl_network_internet_gateway_v2.this.region
}

output "status" {
  description = "returns a string"
  value       = data.ecl_network_internet_gateway_v2.this.status
}

output "tenant_id" {
  description = "returns a string"
  value       = data.ecl_network_internet_gateway_v2.this.tenant_id
}

output "this" {
  value = ecl_network_internet_gateway_v2.this
}
```

[top](#index)