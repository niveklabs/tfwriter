# ecl_network_public_ip_v2

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
module "ecl_network_public_ip_v2" {
  source = "./modules/ecl/d/ecl_network_public_ip_v2"

  # cidr - (optional) is a type of string
  cidr = null
  # description - (optional) is a type of string
  description = null
  # internet_gw_id - (optional) is a type of string
  internet_gw_id = null
  # name - (optional) is a type of string
  name = null
  # public_ip_id - (optional) is a type of string
  public_ip_id = null
  # region - (optional) is a type of string
  region = null
  # status - (optional) is a type of string
  status = null
  # submask_length - (optional) is a type of number
  submask_length = null
  # tenant_id - (optional) is a type of string
  tenant_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_gw_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public_ip_id" {
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

variable "submask_length" {
  description = "(optional)"
  type        = number
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
data "ecl_network_public_ip_v2" "this" {
  cidr           = var.cidr
  description    = var.description
  internet_gw_id = var.internet_gw_id
  name           = var.name
  public_ip_id   = var.public_ip_id
  region         = var.region
  status         = var.status
  submask_length = var.submask_length
  tenant_id      = var.tenant_id
}
```

[top](#index)

### Outputs

```terraform
output "cidr" {
  description = "returns a string"
  value       = data.ecl_network_public_ip_v2.this.cidr
}

output "description" {
  description = "returns a string"
  value       = data.ecl_network_public_ip_v2.this.description
}

output "id" {
  description = "returns a string"
  value       = data.ecl_network_public_ip_v2.this.id
}

output "internet_gw_id" {
  description = "returns a string"
  value       = data.ecl_network_public_ip_v2.this.internet_gw_id
}

output "name" {
  description = "returns a string"
  value       = data.ecl_network_public_ip_v2.this.name
}

output "public_ip_id" {
  description = "returns a string"
  value       = data.ecl_network_public_ip_v2.this.public_ip_id
}

output "region" {
  description = "returns a string"
  value       = data.ecl_network_public_ip_v2.this.region
}

output "status" {
  description = "returns a string"
  value       = data.ecl_network_public_ip_v2.this.status
}

output "submask_length" {
  description = "returns a number"
  value       = data.ecl_network_public_ip_v2.this.submask_length
}

output "tenant_id" {
  description = "returns a string"
  value       = data.ecl_network_public_ip_v2.this.tenant_id
}

output "this" {
  value = ecl_network_public_ip_v2.this
}
```

[top](#index)