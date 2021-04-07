# aviatrix_vpc

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_vpc" {
  source = "./modules/aviatrix/d/aviatrix_vpc"

  # name - (required) is a type of string
  name = null
  # route_tables_filter - (optional) is a type of string
  route_tables_filter = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the VPC created."
  type        = string
}

variable "route_tables_filter" {
  description = "(optional) - Filters the route_tables list to contain only public or private route tables. Valid values are 'private' or 'public'. If not set then route_tables are not filtered."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aviatrix_vpc" "this" {
  # name - (required) is a type of string
  name = var.name
  # route_tables_filter - (optional) is a type of string
  route_tables_filter = var.route_tables_filter
}
```

[top](#index)

### Outputs

```terraform
output "account_name" {
  description = "returns a string"
  value       = data.aviatrix_vpc.this.account_name
}

output "aviatrix_firenet_vpc" {
  description = "returns a bool"
  value       = data.aviatrix_vpc.this.aviatrix_firenet_vpc
}

output "aviatrix_transit_vpc" {
  description = "returns a bool"
  value       = data.aviatrix_vpc.this.aviatrix_transit_vpc
}

output "azure_vnet_resource_id" {
  description = "returns a string"
  value       = data.aviatrix_vpc.this.azure_vnet_resource_id
}

output "cidr" {
  description = "returns a string"
  value       = data.aviatrix_vpc.this.cidr
}

output "cloud_type" {
  description = "returns a number"
  value       = data.aviatrix_vpc.this.cloud_type
}

output "id" {
  description = "returns a string"
  value       = data.aviatrix_vpc.this.id
}

output "num_of_subnet_pairs" {
  description = "returns a number"
  value       = data.aviatrix_vpc.this.num_of_subnet_pairs
}

output "private_subnets" {
  description = "returns a list of object"
  value       = data.aviatrix_vpc.this.private_subnets
}

output "public_subnets" {
  description = "returns a list of object"
  value       = data.aviatrix_vpc.this.public_subnets
}

output "region" {
  description = "returns a string"
  value       = data.aviatrix_vpc.this.region
}

output "resource_group" {
  description = "returns a string"
  value       = data.aviatrix_vpc.this.resource_group
}

output "route_tables" {
  description = "returns a list of string"
  value       = data.aviatrix_vpc.this.route_tables
}

output "subnet_size" {
  description = "returns a number"
  value       = data.aviatrix_vpc.this.subnet_size
}

output "subnets" {
  description = "returns a list of object"
  value       = data.aviatrix_vpc.this.subnets
}

output "vpc_id" {
  description = "returns a string"
  value       = data.aviatrix_vpc.this.vpc_id
}

output "this" {
  value = aviatrix_vpc.this
}
```

[top](#index)