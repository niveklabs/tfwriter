# aci_cloud_subnet

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_cloud_subnet" {
  source = "./modules/aci/d/aci_cloud_subnet"

  # annotation - (optional) is a type of string
  annotation = null
  # cloud_cidr_pool_dn - (required) is a type of string
  cloud_cidr_pool_dn = null
  # description - (optional) is a type of string
  description = null
  # ip - (required) is a type of string
  ip = null
  # name - (optional) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # scope - (optional) is a type of string
  scope = null
  # usage - (optional) is a type of string
  usage = null
}
```

[top](#index)

### Variables

```terraform
variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cloud_cidr_pool_dn" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "usage" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aci_cloud_subnet" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # cloud_cidr_pool_dn - (required) is a type of string
  cloud_cidr_pool_dn = var.cloud_cidr_pool_dn
  # description - (optional) is a type of string
  description = var.description
  # ip - (required) is a type of string
  ip = var.ip
  # name - (optional) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # scope - (optional) is a type of string
  scope = var.scope
  # usage - (optional) is a type of string
  usage = var.usage
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_cloud_subnet.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_cloud_subnet.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aci_cloud_subnet.this.name
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_cloud_subnet.this.name_alias
}

output "scope" {
  description = "returns a string"
  value       = data.aci_cloud_subnet.this.scope
}

output "usage" {
  description = "returns a string"
  value       = data.aci_cloud_subnet.this.usage
}

output "this" {
  value = aci_cloud_subnet.this
}
```

[top](#index)