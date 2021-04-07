# consul_nodes

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
module "consul_nodes" {
  source = "./modules/consul/d/consul_nodes"


  query_options = [{
    allow_stale        = null
    datacenter         = null
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
data "consul_nodes" "this" {

  dynamic "query_options" {
    for_each = var.query_options
    content {
      # allow_stale - (optional) is a type of bool
      allow_stale = query_options.value["allow_stale"]
      # datacenter - (optional) is a type of string
      datacenter = query_options.value["datacenter"]
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
output "datacenter" {
  description = "returns a string"
  value       = data.consul_nodes.this.datacenter
}

output "id" {
  description = "returns a string"
  value       = data.consul_nodes.this.id
}

output "node_ids" {
  description = "returns a list of string"
  value       = data.consul_nodes.this.node_ids
}

output "node_names" {
  description = "returns a list of string"
  value       = data.consul_nodes.this.node_names
}

output "nodes" {
  description = "returns a list of object"
  value       = data.consul_nodes.this.nodes
}

output "this" {
  value = consul_nodes.this
}
```

[top](#index)