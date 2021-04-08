# vra_region

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vra = ">= 0.3.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vra_region" {
  source = "./modules/vra/d/vra_region"

  # cloud_account_id - (optional) is a type of string
  cloud_account_id = null
  # filter - (optional) is a type of string
  filter = null
  # name - (optional) is a type of string
  name = null
  # org_id - (optional) is a type of string
  org_id = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "cloud_account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "org_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vra_region" "this" {
  # cloud_account_id - (optional) is a type of string
  cloud_account_id = var.cloud_account_id
  # filter - (optional) is a type of string
  filter = var.filter
  # name - (optional) is a type of string
  name = var.name
  # org_id - (optional) is a type of string
  org_id = var.org_id
  # region - (optional) is a type of string
  region = var.region
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = data.vra_region.this.created_at
}

output "external_region_id" {
  description = "returns a string"
  value       = data.vra_region.this.external_region_id
}

output "id" {
  description = "returns a string"
  value       = data.vra_region.this.id
}

output "owner" {
  description = "returns a string"
  value       = data.vra_region.this.owner
}

output "updated_at" {
  description = "returns a string"
  value       = data.vra_region.this.updated_at
}

output "this" {
  value = vra_region.this
}
```

[top](#index)