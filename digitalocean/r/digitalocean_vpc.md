# digitalocean_vpc

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "digitalocean_vpc" {
  source = "./modules/digitalocean/r/digitalocean_vpc"

  # description - (optional) is a type of string
  description = null
  # ip_range - (optional) is a type of string
  ip_range = null
  # name - (required) is a type of string
  name = null
  # region - (required) is a type of string
  region = null

  timeouts = [{
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - A free-form description for the VPC"
  type        = string
  default     = null
}

variable "ip_range" {
  description = "(optional) - The range of IP addresses for the VPC in CIDR notation"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the VPC"
  type        = string
}

variable "region" {
  description = "(required) - DigitalOcean region slug for the VPC's location"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_vpc" "this" {
  # description - (optional) is a type of string
  description = var.description
  # ip_range - (optional) is a type of string
  ip_range = var.ip_range
  # name - (required) is a type of string
  name = var.name
  # region - (required) is a type of string
  region = var.region

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = digitalocean_vpc.this.created_at
}

output "default" {
  description = "returns a bool"
  value       = digitalocean_vpc.this.default
}

output "id" {
  description = "returns a string"
  value       = digitalocean_vpc.this.id
}

output "ip_range" {
  description = "returns a string"
  value       = digitalocean_vpc.this.ip_range
}

output "urn" {
  description = "returns a string"
  value       = digitalocean_vpc.this.urn
}

output "this" {
  value = digitalocean_vpc.this
}
```

[top](#index)