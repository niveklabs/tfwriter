# nomad_job_parser

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
    nomad = ">= 1.4.14"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nomad_job_parser" {
  source = "./modules/nomad/d/nomad_job_parser"

  # canonicalize - (optional) is a type of bool
  canonicalize = null
  # hcl - (required) is a type of string
  hcl = null
}
```

[top](#index)

### Variables

```terraform
variable "canonicalize" {
  description = "(optional) - Flag to enable setting any unset fields to their default values."
  type        = bool
  default     = null
}

variable "hcl" {
  description = "(required) - Specifies the HCL definition of the job encoded in a JSON string."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "nomad_job_parser" "this" {
  canonicalize = var.canonicalize
  hcl          = var.hcl
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.nomad_job_parser.this.id
}

output "json" {
  description = "returns a string"
  value       = data.nomad_job_parser.this.json
}

output "this" {
  value = nomad_job_parser.this
}
```

[top](#index)