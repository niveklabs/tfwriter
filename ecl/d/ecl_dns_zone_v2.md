# ecl_dns_zone_v2

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
module "ecl_dns_zone_v2" {
  source = "./modules/ecl/d/ecl_dns_zone_v2"

  # attributes - (optional) is a type of map of string
  attributes = {}
  # created_at - (optional) is a type of string
  created_at = null
  # description - (optional) is a type of string
  description = null
  # domain_name - (optional) is a type of string
  domain_name = null
  # email - (optional) is a type of string
  email = null
  # masters - (optional) is a type of set of string
  masters = []
  # name - (optional) is a type of string
  name = null
  # pool_id - (optional) is a type of string
  pool_id = null
  # project_id - (optional) is a type of string
  project_id = null
  # region - (optional) is a type of string
  region = null
  # serial - (optional) is a type of number
  serial = null
  # status - (optional) is a type of string
  status = null
  # transferred_at - (optional) is a type of string
  transferred_at = null
  # ttl - (optional) is a type of number
  ttl = null
  # type - (optional) is a type of string
  type = null
  # updated_at - (optional) is a type of string
  updated_at = null
  # version - (optional) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "attributes" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "created_at" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "masters" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pool_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "serial" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "transferred_at" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "updated_at" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ecl_dns_zone_v2" "this" {
  # attributes - (optional) is a type of map of string
  attributes = var.attributes
  # created_at - (optional) is a type of string
  created_at = var.created_at
  # description - (optional) is a type of string
  description = var.description
  # domain_name - (optional) is a type of string
  domain_name = var.domain_name
  # email - (optional) is a type of string
  email = var.email
  # masters - (optional) is a type of set of string
  masters = var.masters
  # name - (optional) is a type of string
  name = var.name
  # pool_id - (optional) is a type of string
  pool_id = var.pool_id
  # project_id - (optional) is a type of string
  project_id = var.project_id
  # region - (optional) is a type of string
  region = var.region
  # serial - (optional) is a type of number
  serial = var.serial
  # status - (optional) is a type of string
  status = var.status
  # transferred_at - (optional) is a type of string
  transferred_at = var.transferred_at
  # ttl - (optional) is a type of number
  ttl = var.ttl
  # type - (optional) is a type of string
  type = var.type
  # updated_at - (optional) is a type of string
  updated_at = var.updated_at
  # version - (optional) is a type of number
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "attributes" {
  description = "returns a map of string"
  value       = data.ecl_dns_zone_v2.this.attributes
}

output "created_at" {
  description = "returns a string"
  value       = data.ecl_dns_zone_v2.this.created_at
}

output "description" {
  description = "returns a string"
  value       = data.ecl_dns_zone_v2.this.description
}

output "domain_name" {
  description = "returns a string"
  value       = data.ecl_dns_zone_v2.this.domain_name
}

output "email" {
  description = "returns a string"
  value       = data.ecl_dns_zone_v2.this.email
}

output "id" {
  description = "returns a string"
  value       = data.ecl_dns_zone_v2.this.id
}

output "masters" {
  description = "returns a set of string"
  value       = data.ecl_dns_zone_v2.this.masters
}

output "name" {
  description = "returns a string"
  value       = data.ecl_dns_zone_v2.this.name
}

output "pool_id" {
  description = "returns a string"
  value       = data.ecl_dns_zone_v2.this.pool_id
}

output "project_id" {
  description = "returns a string"
  value       = data.ecl_dns_zone_v2.this.project_id
}

output "region" {
  description = "returns a string"
  value       = data.ecl_dns_zone_v2.this.region
}

output "serial" {
  description = "returns a number"
  value       = data.ecl_dns_zone_v2.this.serial
}

output "status" {
  description = "returns a string"
  value       = data.ecl_dns_zone_v2.this.status
}

output "transferred_at" {
  description = "returns a string"
  value       = data.ecl_dns_zone_v2.this.transferred_at
}

output "ttl" {
  description = "returns a number"
  value       = data.ecl_dns_zone_v2.this.ttl
}

output "type" {
  description = "returns a string"
  value       = data.ecl_dns_zone_v2.this.type
}

output "updated_at" {
  description = "returns a string"
  value       = data.ecl_dns_zone_v2.this.updated_at
}

output "version" {
  description = "returns a number"
  value       = data.ecl_dns_zone_v2.this.version
}

output "this" {
  value = ecl_dns_zone_v2.this
}
```

[top](#index)