# consul_catalog_service

[back](../consul.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    consul = ">= 2.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "consul_catalog_service" {
  source = "./modules/consul/d/consul_catalog_service"

  # datacenter - (optional) is a type of string
  datacenter = null
  # filter - (optional) is a type of string
  filter = null
  # name - (required) is a type of string
  name = null
  # tag - (optional) is a type of string
  tag = null

  query_options = [{
    allow_stale        = null
    datacenter         = null
    namespace          = null
    near               = null
    node_meta          = {}
    require_consistent = null
    token              = null
    wait_index         = null
    wait_time          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "datacenter" {
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
  description = "(required)"
  type        = string
}

variable "tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "query_options" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      allow_stale        = bool
      datacenter         = string
      namespace          = string
      near               = string
      node_meta          = map(string)
      require_consistent = bool
      token              = string
      wait_index         = number
      wait_time          = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "consul_catalog_service" "this" {
  # datacenter - (optional) is a type of string
  datacenter = var.datacenter
  # filter - (optional) is a type of string
  filter = var.filter
  # name - (required) is a type of string
  name = var.name
  # tag - (optional) is a type of string
  tag = var.tag

  dynamic "query_options" {
    for_each = var.query_options
    content {
      # allow_stale - (optional) is a type of bool
      allow_stale = query_options.value["allow_stale"]
      # datacenter - (optional) is a type of string
      datacenter = query_options.value["datacenter"]
      # namespace - (optional) is a type of string
      namespace = query_options.value["namespace"]
      # near - (optional) is a type of string
      near = query_options.value["near"]
      # node_meta - (optional) is a type of map of string
      node_meta = query_options.value["node_meta"]
      # require_consistent - (optional) is a type of bool
      require_consistent = query_options.value["require_consistent"]
      # token - (optional) is a type of string
      token = query_options.value["token"]
      # wait_index - (optional) is a type of number
      wait_index = query_options.value["wait_index"]
      # wait_time - (optional) is a type of string
      wait_time = query_options.value["wait_time"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.consul_catalog_service.this.id
}

output "service" {
  description = "returns a list of object"
  value       = data.consul_catalog_service.this.service
}

output "this" {
  value = consul_catalog_service.this
}
```

[top](#index)