# hcloud_location

[back](../hcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcloud = ">= 1.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcloud_location" {
  source = "./modules/hcloud/d/hcloud_location"

  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "hcloud_location" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "city" {
  description = "returns a string"
  value       = data.hcloud_location.this.city
}

output "country" {
  description = "returns a string"
  value       = data.hcloud_location.this.country
}

output "description" {
  description = "returns a string"
  value       = data.hcloud_location.this.description
}

output "id" {
  description = "returns a number"
  value       = data.hcloud_location.this.id
}

output "latitude" {
  description = "returns a number"
  value       = data.hcloud_location.this.latitude
}

output "longitude" {
  description = "returns a number"
  value       = data.hcloud_location.this.longitude
}

output "name" {
  description = "returns a string"
  value       = data.hcloud_location.this.name
}

output "this" {
  value = hcloud_location.this
}
```

[top](#index)