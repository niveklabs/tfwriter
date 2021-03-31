# fortios_system_vdomsflow

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
module "fortios_system_vdomsflow" {
  source = "./modules/fortios/d/fortios_system_vdomsflow"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_vdomsflow" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "collector_ip" {
  description = "returns a string"
  value       = data.fortios_system_vdomsflow.this.collector_ip
}

output "collector_port" {
  description = "returns a number"
  value       = data.fortios_system_vdomsflow.this.collector_port
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_vdomsflow.this.id
}

output "source_ip" {
  description = "returns a string"
  value       = data.fortios_system_vdomsflow.this.source_ip
}

output "vdom_sflow" {
  description = "returns a string"
  value       = data.fortios_system_vdomsflow.this.vdom_sflow
}

output "this" {
  value = fortios_system_vdomsflow.this
}
```

[top](#index)