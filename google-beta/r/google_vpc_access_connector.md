# google_vpc_access_connector

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_vpc_access_connector" {
  source = "./modules/google-beta/r/google_vpc_access_connector"

  # ip_cidr_range - (required) is a type of string
  ip_cidr_range = null
  # max_throughput - (optional) is a type of number
  max_throughput = null
  # min_throughput - (optional) is a type of number
  min_throughput = null
  # name - (required) is a type of string
  name = null
  # network - (required) is a type of string
  network = null
  # project - (optional) is a type of string
  project = null
  # region - (required) is a type of string
  region = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "ip_cidr_range" {
  description = "(required) - The range of internal addresses that follows RFC 4632 notation. Example: '10.132.0.0/28'."
  type        = string
}

variable "max_throughput" {
  description = "(optional) - Maximum throughput of the connector in Mbps, must be greater than 'min_throughput'. Default is 1000."
  type        = number
  default     = null
}

variable "min_throughput" {
  description = "(optional) - Minimum throughput of the connector in Mbps. Default and min is 200."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - The name of the resource (Max 25 characters)."
  type        = string
}

variable "network" {
  description = "(required) - Name of a VPC network."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(required) - Region where the VPC Access connector resides"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_vpc_access_connector" "this" {
  ip_cidr_range  = var.ip_cidr_range
  max_throughput = var.max_throughput
  min_throughput = var.min_throughput
  name           = var.name
  network        = var.network
  project        = var.project
  region         = var.region

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_vpc_access_connector.this.id
}

output "project" {
  description = "returns a string"
  value       = google_vpc_access_connector.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_vpc_access_connector.this.self_link
}

output "state" {
  description = "returns a string"
  value       = google_vpc_access_connector.this.state
}

output "this" {
  value = google_vpc_access_connector.this
}
```

[top](#index)