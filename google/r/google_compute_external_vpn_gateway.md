# google_compute_external_vpn_gateway

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_external_vpn_gateway" {
  source = "./modules/google/r/google_compute_external_vpn_gateway"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # redundancy_type - (optional) is a type of string
  redundancy_type = null

  interface = [{
    id         = null
    ip_address = null
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
variable "description" {
  description = "(optional) - An optional description of this resource."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource. Provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035.  Specifically, the name must be 1-63 characters long and\nmatch the regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means\nthe first character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "redundancy_type" {
  description = "(optional) - Indicates the redundancy type of this external VPN gateway Possible values: [\"FOUR_IPS_REDUNDANCY\", \"SINGLE_IP_INTERNALLY_REDUNDANT\", \"TWO_IPS_REDUNDANCY\"]"
  type        = string
  default     = null
}

variable "interface" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id         = number
      ip_address = string
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
resource "google_compute_external_vpn_gateway" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
  # redundancy_type - (optional) is a type of string
  redundancy_type = var.redundancy_type

  dynamic "interface" {
    for_each = var.interface
    content {
      # id - (optional) is a type of number
      id = interface.value["id"]
      # ip_address - (optional) is a type of string
      ip_address = interface.value["ip_address"]
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
  value       = google_compute_external_vpn_gateway.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_external_vpn_gateway.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_external_vpn_gateway.this.self_link
}

output "this" {
  value = google_compute_external_vpn_gateway.this
}
```

[top](#index)