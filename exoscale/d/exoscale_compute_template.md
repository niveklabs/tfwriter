# exoscale_compute_template

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
module "exoscale_compute_template" {
  source = "./modules/exoscale/d/exoscale_compute_template"

  # filter - (optional) is a type of string
  filter = null
  # name - (optional) is a type of string
  name = null
  # zone - (required) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "(optional) - Template filter to apply"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the template"
  type        = string
  default     = null
}

variable "zone" {
  description = "(required) - Name of the zone"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "exoscale_compute_template" "this" {
  filter = var.filter
  name   = var.name
  zone   = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.exoscale_compute_template.this.id
}

output "username" {
  description = "returns a string"
  value       = data.exoscale_compute_template.this.username
}

output "this" {
  value = exoscale_compute_template.this
}
```

[top](#index)