# vra_data_collector

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vra = ">= 0.3.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vra_data_collector" {
  source = "./modules/vra/d/vra_data_collector"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vra_data_collector" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "hostname" {
  description = "returns a string"
  value       = data.vra_data_collector.this.hostname
}

output "id" {
  description = "returns a string"
  value       = data.vra_data_collector.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = data.vra_data_collector.this.ip_address
}

output "status" {
  description = "returns a string"
  value       = data.vra_data_collector.this.status
}

output "this" {
  value = vra_data_collector.this
}
```

[top](#index)