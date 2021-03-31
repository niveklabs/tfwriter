# fortios_system_sflow

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
module "fortios_system_sflow" {
  source = "./modules/fortios/d/fortios_system_sflow"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_sflow" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "collector_ip" {
  description = "returns a string"
  value       = data.fortios_system_sflow.this.collector_ip
}

output "collector_port" {
  description = "returns a number"
  value       = data.fortios_system_sflow.this.collector_port
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_sflow.this.id
}

output "source_ip" {
  description = "returns a string"
  value       = data.fortios_system_sflow.this.source_ip
}

output "this" {
  value = fortios_system_sflow.this
}
```

[top](#index)