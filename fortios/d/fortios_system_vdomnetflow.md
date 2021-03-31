# fortios_system_vdomnetflow

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
module "fortios_system_vdomnetflow" {
  source = "./modules/fortios/d/fortios_system_vdomnetflow"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_vdomnetflow" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "collector_ip" {
  description = "returns a string"
  value       = data.fortios_system_vdomnetflow.this.collector_ip
}

output "collector_port" {
  description = "returns a number"
  value       = data.fortios_system_vdomnetflow.this.collector_port
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_vdomnetflow.this.id
}

output "source_ip" {
  description = "returns a string"
  value       = data.fortios_system_vdomnetflow.this.source_ip
}

output "vdom_netflow" {
  description = "returns a string"
  value       = data.fortios_system_vdomnetflow.this.vdom_netflow
}

output "this" {
  value = fortios_system_vdomnetflow.this
}
```

[top](#index)