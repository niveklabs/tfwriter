# google_dns_policy

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
module "google_dns_policy" {
  source = "./modules/google/r/google_dns_policy"

  # description - (optional) is a type of string
  description = null
  # enable_inbound_forwarding - (optional) is a type of bool
  enable_inbound_forwarding = null
  # enable_logging - (optional) is a type of bool
  enable_logging = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null

  alternative_name_server_config = [{
    target_name_servers = [{
      forwarding_path = null
      ipv4_address    = null
    }]
  }]

  networks = [{
    network_url = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - A textual description field. Defaults to 'Managed by Terraform'."
  type        = string
  default     = null
}

variable "enable_inbound_forwarding" {
  description = "(optional) - Allows networks bound to this policy to receive DNS queries sent\nby VMs or applications over VPN connections. When enabled, a\nvirtual IP address will be allocated from each of the sub-networks\nthat are bound to this policy."
  type        = bool
  default     = null
}

variable "enable_logging" {
  description = "(optional) - Controls whether logging is enabled for the networks bound to this policy.\nDefaults to no logging if not set."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - User assigned name for this policy."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alternative_name_server_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      target_name_servers = set(object(
        {
          forwarding_path = string
          ipv4_address    = string
        }
      ))
    }
  ))
  default = []
}

variable "networks" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      network_url = string
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_dns_policy" "this" {
  # description - (optional) is a type of string
  description = var.description
  # enable_inbound_forwarding - (optional) is a type of bool
  enable_inbound_forwarding = var.enable_inbound_forwarding
  # enable_logging - (optional) is a type of bool
  enable_logging = var.enable_logging
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project

  dynamic "alternative_name_server_config" {
    for_each = var.alternative_name_server_config
    content {

      dynamic "target_name_servers" {
        for_each = alternative_name_server_config.value.target_name_servers
        content {
          # forwarding_path - (optional) is a type of string
          forwarding_path = target_name_servers.value["forwarding_path"]
          # ipv4_address - (required) is a type of string
          ipv4_address = target_name_servers.value["ipv4_address"]
        }
      }

    }
  }

  dynamic "networks" {
    for_each = var.networks
    content {
      # network_url - (required) is a type of string
      network_url = networks.value["network_url"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_dns_policy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_dns_policy.this.project
}

output "this" {
  value = google_dns_policy.this
}
```

[top](#index)