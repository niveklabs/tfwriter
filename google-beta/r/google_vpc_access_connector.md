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
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_vpc_access_connector" {
  source = "./modules/google-beta/r/google_vpc_access_connector"

  # ip_cidr_range - (optional) is a type of string
  ip_cidr_range = null
  # machine_type - (optional) is a type of string
  machine_type = null
  # max_instances - (optional) is a type of number
  max_instances = null
  # max_throughput - (optional) is a type of number
  max_throughput = null
  # min_instances - (optional) is a type of number
  min_instances = null
  # min_throughput - (optional) is a type of number
  min_throughput = null
  # name - (required) is a type of string
  name = null
  # network - (optional) is a type of string
  network = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null

  subnet = [{
    name       = null
    project_id = null
  }]

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
  description = "(optional) - The range of internal addresses that follows RFC 4632 notation. Example: '10.132.0.0/28'."
  type        = string
  default     = null
}

variable "machine_type" {
  description = "(optional) - Machine type of VM Instance underlying connector. Default is e2-micro"
  type        = string
  default     = null
}

variable "max_instances" {
  description = "(optional) - Maximum value of instances in autoscaling group underlying the connector."
  type        = number
  default     = null
}

variable "max_throughput" {
  description = "(optional) - Maximum throughput of the connector in Mbps, must be greater than 'min_throughput'. Default is 1000."
  type        = number
  default     = null
}

variable "min_instances" {
  description = "(optional) - Minimum value of instances in autoscaling group underlying the connector."
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
  description = "(optional) - Name of the VPC network. Required if 'ip_cidr_range' is set."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - Region where the VPC Access connector resides. If it is not provided, the provider region is used."
  type        = string
  default     = null
}

variable "subnet" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      name       = string
      project_id = string
    }
  ))
  default = []
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
  # ip_cidr_range - (optional) is a type of string
  ip_cidr_range = var.ip_cidr_range
  # machine_type - (optional) is a type of string
  machine_type = var.machine_type
  # max_instances - (optional) is a type of number
  max_instances = var.max_instances
  # max_throughput - (optional) is a type of number
  max_throughput = var.max_throughput
  # min_instances - (optional) is a type of number
  min_instances = var.min_instances
  # min_throughput - (optional) is a type of number
  min_throughput = var.min_throughput
  # name - (required) is a type of string
  name = var.name
  # network - (optional) is a type of string
  network = var.network
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region

  dynamic "subnet" {
    for_each = var.subnet
    content {
      # name - (optional) is a type of string
      name = subnet.value["name"]
      # project_id - (optional) is a type of string
      project_id = subnet.value["project_id"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
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

output "max_instances" {
  description = "returns a number"
  value       = google_vpc_access_connector.this.max_instances
}

output "min_instances" {
  description = "returns a number"
  value       = google_vpc_access_connector.this.min_instances
}

output "project" {
  description = "returns a string"
  value       = google_vpc_access_connector.this.project
}

output "region" {
  description = "returns a string"
  value       = google_vpc_access_connector.this.region
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