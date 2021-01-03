# nomad_scheduler_config

[back](../nomad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nomad = ">= 1.4.11"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nomad_scheduler_config" {
  source = "./modules/nomad/d/nomad_scheduler_config"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "nomad_scheduler_config" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.nomad_scheduler_config.this.id
}

output "preemption_config" {
  description = "returns a map of bool"
  value       = data.nomad_scheduler_config.this.preemption_config
}

output "scheduler_algorithm" {
  description = "returns a string"
  value       = data.nomad_scheduler_config.this.scheduler_algorithm
}

output "this" {
  value = nomad_scheduler_config.this
}
```

[top](#index)