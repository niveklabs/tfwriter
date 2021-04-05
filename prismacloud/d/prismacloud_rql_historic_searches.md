# prismacloud_rql_historic_searches

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
module "prismacloud_rql_historic_searches" {
  source = "./modules/prismacloud/d/prismacloud_rql_historic_searches"

  # filter - (optional) is a type of string
  filter = null
  # limit - (optional) is a type of number
  limit = null
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "(optional) - Filter for historic RQL searches"
  type        = string
  default     = null
}

variable "limit" {
  description = "(optional) - Max number of historic RQL searches to return"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "prismacloud_rql_historic_searches" "this" {
  filter = var.filter
  limit  = var.limit
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.prismacloud_rql_historic_searches.this.id
}

output "listing" {
  description = "returns a list of object"
  value       = data.prismacloud_rql_historic_searches.this.listing
}

output "total" {
  description = "returns a number"
  value       = data.prismacloud_rql_historic_searches.this.total
}

output "this" {
  value = prismacloud_rql_historic_searches.this
}
```

[top](#index)