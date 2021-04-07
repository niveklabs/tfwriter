# prismacloud_rql_historic_search

[back](../prismacloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    prismacloud = ">= 1.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "prismacloud_rql_historic_search" {
  source = "./modules/prismacloud/d/prismacloud_rql_historic_search"

  # name - (optional) is a type of string
  name = null
  # search_id - (optional) is a type of string
  search_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Historic RQL search name"
  type        = string
  default     = null
}

variable "search_id" {
  description = "(optional) - Historic RQL search ID"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "prismacloud_rql_historic_search" "this" {
  # name - (optional) is a type of string
  name = var.name
  # search_id - (optional) is a type of string
  search_id = var.search_id
}
```

[top](#index)

### Outputs

```terraform
output "cloud_type" {
  description = "returns a string"
  value       = data.prismacloud_rql_historic_search.this.cloud_type
}

output "description" {
  description = "returns a string"
  value       = data.prismacloud_rql_historic_search.this.description
}

output "id" {
  description = "returns a string"
  value       = data.prismacloud_rql_historic_search.this.id
}

output "name" {
  description = "returns a string"
  value       = data.prismacloud_rql_historic_search.this.name
}

output "query" {
  description = "returns a string"
  value       = data.prismacloud_rql_historic_search.this.query
}

output "saved" {
  description = "returns a bool"
  value       = data.prismacloud_rql_historic_search.this.saved
}

output "search_id" {
  description = "returns a string"
  value       = data.prismacloud_rql_historic_search.this.search_id
}

output "search_type" {
  description = "returns a string"
  value       = data.prismacloud_rql_historic_search.this.search_type
}

output "time_range" {
  description = "returns a list of object"
  value       = data.prismacloud_rql_historic_search.this.time_range
}

output "this" {
  value = prismacloud_rql_historic_search.this
}
```

[top](#index)