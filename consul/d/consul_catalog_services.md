# consul_catalog_services

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
module "consul_catalog_services" {
  source = "./modules/consul/d/consul_catalog_services"


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
data "consul_catalog_services" "this" {

  dynamic "query_options" {
    for_each = var.query_options
    content {
      allow_stale        = query_options.value["allow_stale"]
      datacenter         = query_options.value["datacenter"]
      namespace          = query_options.value["namespace"]
      near               = query_options.value["near"]
      node_meta          = query_options.value["node_meta"]
      require_consistent = query_options.value["require_consistent"]
      token              = query_options.value["token"]
      wait_index         = query_options.value["wait_index"]
      wait_time          = query_options.value["wait_time"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "datacenter" {
  description = "returns a string"
  value       = data.consul_catalog_services.this.datacenter
}

output "id" {
  description = "returns a string"
  value       = data.consul_catalog_services.this.id
}

output "names" {
  description = "returns a list of string"
  value       = data.consul_catalog_services.this.names
}

output "services" {
  description = "returns a map of string"
  value       = data.consul_catalog_services.this.services
}

output "this" {
  value = consul_catalog_services.this
}
```

[top](#index)