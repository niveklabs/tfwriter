# nomad_scaling_policy

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
    nomad = ">= 1.4.13"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nomad_scaling_policy" {
  source = "./modules/nomad/d/nomad_scaling_policy"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "nomad_scaling_policy" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "enabled" {
  description = "returns a bool"
  value       = data.nomad_scaling_policy.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.nomad_scaling_policy.this.id
}

output "max" {
  description = "returns a number"
  value       = data.nomad_scaling_policy.this.max
}

output "min" {
  description = "returns a number"
  value       = data.nomad_scaling_policy.this.min
}

output "policy" {
  description = "returns a string"
  value       = data.nomad_scaling_policy.this.policy
}

output "target" {
  description = "returns a map of string"
  value       = data.nomad_scaling_policy.this.target
}

output "type" {
  description = "returns a string"
  value       = data.nomad_scaling_policy.this.type
}

output "this" {
  value = nomad_scaling_policy.this
}
```

[top](#index)