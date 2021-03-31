# nomad_scaling_policies

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
module "nomad_scaling_policies" {
  source = "./modules/nomad/d/nomad_scaling_policies"

  # job_id - (optional) is a type of string
  job_id = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "job_id" {
  description = "(optional) - Job ID to use to filter scaling policies."
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - Scaling policy type used to filter scaling policies."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nomad_scaling_policies" "this" {
  job_id = var.job_id
  type   = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.nomad_scaling_policies.this.id
}

output "policies" {
  description = "returns a list of object"
  value       = data.nomad_scaling_policies.this.policies
}

output "this" {
  value = nomad_scaling_policies.this
}
```

[top](#index)