# hcloud_locations

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
    hcloud = ">= 1.26.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcloud_locations" {
  source = "./modules/hcloud/d/hcloud_locations"

  # location_ids - (optional) is a type of list of string
  location_ids = []
}
```

[top](#index)

### Variables

```terraform
variable "location_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "hcloud_locations" "this" {
  # location_ids - (optional) is a type of list of string
  location_ids = var.location_ids
}
```

[top](#index)

### Outputs

```terraform
output "descriptions" {
  description = "returns a list of string"
  value       = data.hcloud_locations.this.descriptions
}

output "id" {
  description = "returns a string"
  value       = data.hcloud_locations.this.id
}

output "names" {
  description = "returns a list of string"
  value       = data.hcloud_locations.this.names
}

output "this" {
  value = hcloud_locations.this
}
```

[top](#index)