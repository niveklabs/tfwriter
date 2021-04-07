# exoscale_affinity

[back](../exoscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    exoscale = ">= 0.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_affinity" {
  source = "./modules/exoscale/d/exoscale_affinity"

  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Name of the Affinity Group"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "exoscale_affinity" "this" {
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.exoscale_affinity.this.id
}

output "this" {
  value = exoscale_affinity.this
}
```

[top](#index)