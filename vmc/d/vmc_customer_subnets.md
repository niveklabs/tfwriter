# vmc_customer_subnets

[back](../vmc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vmc = ">= 1.5.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vmc_customer_subnets" {
  source = "./modules/vmc/d/vmc_customer_subnets"

  # connected_account_id - (optional) is a type of string
  connected_account_id = null
  # force_refresh - (optional) is a type of bool
  force_refresh = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # num_hosts - (optional) is a type of number
  num_hosts = null
  # region - (required) is a type of string
  region = null
  # sddc_id - (optional) is a type of string
  sddc_id = null
  # sddc_type - (optional) is a type of string
  sddc_type = null
}
```

[top](#index)

### Variables

```terraform
variable "connected_account_id" {
  description = "(optional) - The linked connected account identifier."
  type        = string
  default     = null
}

variable "force_refresh" {
  description = "(optional) - When true, forces the mappings for datacenters to be refreshed for the connected account."
  type        = bool
  default     = null
}

variable "instance_type" {
  description = "(optional) - The server instance type to be used."
  type        = string
  default     = null
}

variable "num_hosts" {
  description = "(optional) - The number of hosts ."
  type        = number
  default     = null
}

variable "region" {
  description = "(required) - The VMC region of the cloud resources to work in. (e.g. US_WEST_2)"
  type        = string
}

variable "sddc_id" {
  description = "(optional) - Sddc ID."
  type        = string
  default     = null
}

variable "sddc_type" {
  description = "(optional) - Sddc Type."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vmc_customer_subnets" "this" {
  # connected_account_id - (optional) is a type of string
  connected_account_id = var.connected_account_id
  # force_refresh - (optional) is a type of bool
  force_refresh = var.force_refresh
  # instance_type - (optional) is a type of string
  instance_type = var.instance_type
  # num_hosts - (optional) is a type of number
  num_hosts = var.num_hosts
  # region - (required) is a type of string
  region = var.region
  # sddc_id - (optional) is a type of string
  sddc_id = var.sddc_id
  # sddc_type - (optional) is a type of string
  sddc_type = var.sddc_type
}
```

[top](#index)

### Outputs

```terraform
output "customer_available_zones" {
  description = "returns a list of string"
  value       = data.vmc_customer_subnets.this.customer_available_zones
}

output "id" {
  description = "returns a string"
  value       = data.vmc_customer_subnets.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.vmc_customer_subnets.this.ids
}

output "vpc_map" {
  description = "returns a map of string"
  value       = data.vmc_customer_subnets.this.vpc_map
}

output "this" {
  value = vmc_customer_subnets.this
}
```

[top](#index)