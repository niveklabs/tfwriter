# digitalocean_volume

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    digitalocean = ">= 2.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_volume" {
  source = "./modules/digitalocean/d/digitalocean_volume"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - volume description"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - name of the volume"
  type        = string
}

variable "region" {
  description = "(optional) - the region that the volume is provisioned in"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_volume" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # region - (optional) is a type of string
  region = var.region
}
```

[top](#index)

### Outputs

```terraform
output "droplet_ids" {
  description = "returns a set of number"
  value       = data.digitalocean_volume.this.droplet_ids
}

output "filesystem_label" {
  description = "returns a string"
  value       = data.digitalocean_volume.this.filesystem_label
}

output "filesystem_type" {
  description = "returns a string"
  value       = data.digitalocean_volume.this.filesystem_type
}

output "id" {
  description = "returns a string"
  value       = data.digitalocean_volume.this.id
}

output "size" {
  description = "returns a number"
  value       = data.digitalocean_volume.this.size
}

output "tags" {
  description = "returns a set of string"
  value       = data.digitalocean_volume.this.tags
}

output "urn" {
  description = "returns a string"
  value       = data.digitalocean_volume.this.urn
}

output "this" {
  value = digitalocean_volume.this
}
```

[top](#index)