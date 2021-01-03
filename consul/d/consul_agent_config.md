# consul_agent_config

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
    consul = ">= 2.10.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "consul_agent_config" {
  source = "./modules/consul/d/consul_agent_config"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "consul_agent_config" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "datacenter" {
  description = "returns a string"
  value       = data.consul_agent_config.this.datacenter
}

output "id" {
  description = "returns a string"
  value       = data.consul_agent_config.this.id
}

output "node_id" {
  description = "returns a string"
  value       = data.consul_agent_config.this.node_id
}

output "node_name" {
  description = "returns a string"
  value       = data.consul_agent_config.this.node_name
}

output "revision" {
  description = "returns a string"
  value       = data.consul_agent_config.this.revision
}

output "server" {
  description = "returns a bool"
  value       = data.consul_agent_config.this.server
}

output "version" {
  description = "returns a string"
  value       = data.consul_agent_config.this.version
}

output "this" {
  value = consul_agent_config.this
}
```

[top](#index)