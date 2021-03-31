# fortios_system_netflow

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_netflow" {
  source = "./modules/fortios/d/fortios_system_netflow"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_netflow" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "active_flow_timeout" {
  description = "returns a number"
  value       = data.fortios_system_netflow.this.active_flow_timeout
}

output "collector_ip" {
  description = "returns a string"
  value       = data.fortios_system_netflow.this.collector_ip
}

output "collector_port" {
  description = "returns a number"
  value       = data.fortios_system_netflow.this.collector_port
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_netflow.this.id
}

output "inactive_flow_timeout" {
  description = "returns a number"
  value       = data.fortios_system_netflow.this.inactive_flow_timeout
}

output "source_ip" {
  description = "returns a string"
  value       = data.fortios_system_netflow.this.source_ip
}

output "template_tx_counter" {
  description = "returns a number"
  value       = data.fortios_system_netflow.this.template_tx_counter
}

output "template_tx_timeout" {
  description = "returns a number"
  value       = data.fortios_system_netflow.this.template_tx_timeout
}

output "this" {
  value = fortios_system_netflow.this
}
```

[top](#index)