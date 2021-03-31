# ecl_network_internet_service_v2

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
module "ecl_network_internet_service_v2" {
  source = "./modules/ecl/d/ecl_network_internet_service_v2"

  # description - (optional) is a type of string
  description = null
  # internet_service_id - (optional) is a type of string
  internet_service_id = null
  # minimal_submask_length - (optional) is a type of number
  minimal_submask_length = null
  # name - (optional) is a type of string
  name = null
  # region - (optional) is a type of string
  region = null
  # zone - (optional) is a type of string
  zone = null
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

variable "internet_service_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "minimal_submask_length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ecl_network_internet_service_v2" "this" {
  description            = var.description
  internet_service_id    = var.internet_service_id
  minimal_submask_length = var.minimal_submask_length
  name                   = var.name
  region                 = var.region
  zone                   = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.ecl_network_internet_service_v2.this.description
}

output "id" {
  description = "returns a string"
  value       = data.ecl_network_internet_service_v2.this.id
}

output "internet_service_id" {
  description = "returns a string"
  value       = data.ecl_network_internet_service_v2.this.internet_service_id
}

output "minimal_submask_length" {
  description = "returns a number"
  value       = data.ecl_network_internet_service_v2.this.minimal_submask_length
}

output "name" {
  description = "returns a string"
  value       = data.ecl_network_internet_service_v2.this.name
}

output "region" {
  description = "returns a string"
  value       = data.ecl_network_internet_service_v2.this.region
}

output "zone" {
  description = "returns a string"
  value       = data.ecl_network_internet_service_v2.this.zone
}

output "this" {
  value = ecl_network_internet_service_v2.this
}
```

[top](#index)