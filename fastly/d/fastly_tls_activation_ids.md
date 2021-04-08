# fastly_tls_activation_ids

[back](../fastly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fastly = ">= 0.28.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_tls_activation_ids" {
  source = "./modules/fastly/d/fastly_tls_activation_ids"

  # certificate_id - (optional) is a type of string
  certificate_id = null
}
```

[top](#index)

### Variables

```terraform
variable "certificate_id" {
  description = "(optional) - ID of TLS certificate used to filter activations"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "fastly_tls_activation_ids" "this" {
  # certificate_id - (optional) is a type of string
  certificate_id = var.certificate_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fastly_tls_activation_ids.this.id
}

output "ids" {
  description = "returns a set of string"
  value       = data.fastly_tls_activation_ids.this.ids
}

output "this" {
  value = fastly_tls_activation_ids.this
}
```

[top](#index)