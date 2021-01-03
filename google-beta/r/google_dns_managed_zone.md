# google_dns_managed_zone

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
module "google_dns_managed_zone" {
  source = "./modules/google-beta/r/google_dns_managed_zone"

  # description - (optional) is a type of string
  description = null
  # dns_name - (required) is a type of string
  dns_name = null
  # force_destroy - (optional) is a type of bool
  force_destroy = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # reverse_lookup - (optional) is a type of bool
  reverse_lookup = null
  # visibility - (optional) is a type of string
  visibility = null

  dnssec_config = [{
    default_key_specs = [{
      algorithm  = null
      key_length = null
      key_type   = null
      kind       = null
    }]
    kind          = null
    non_existence = null
    state         = null
  }]

  forwarding_config = [{
    target_name_servers = [{
      forwarding_path = null
      ipv4_address    = null
    }]
  }]

  peering_config = [{
    target_network = [{
      network_url = null
    }]
  }]

  private_visibility_config = [{
    networks = [{
      network_url = null
    }]
  }]

  service_directory_config = [{
    namespace = [{
      namespace_url = null
    }]
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

variable "dns_name" {
  description = "(required) - The DNS name of this managed zone, for instance \"example.com.\"."
  type        = string
}

variable "force_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - A set of key/value label pairs to assign to this ManagedZone."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - User assigned name for this resource.\nMust be unique within the project."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reverse_lookup" {
  description = "(optional) - Specifies if this is a managed reverse lookup zone. If true, Cloud DNS will resolve reverse\nlookup queries using automatically configured records for VPC resources. This only applies\nto networks listed under 'private_visibility_config'."
  type        = bool
  default     = null
}

variable "visibility" {
  description = "(optional) - The zone's visibility: public zones are exposed to the Internet,\nwhile private zones are visible only to Virtual Private Cloud resources. Default value: \"public\" Possible values: [\"private\", \"public\"]"
  type        = string
  default     = null
}

variable "dnssec_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      default_key_specs = list(object(
        {
          algorithm  = string
          key_length = number
          key_type   = string
          kind       = string
        }
      ))
      kind          = string
      non_existence = string
      state         = string
    }
  ))
  default = []
}

variable "forwarding_config" {
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

variable "peering_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      target_network = list(object(
        {
          network_url = string
        }
      ))
    }
  ))
  default = []
}

variable "private_visibility_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      networks = set(object(
        {
          network_url = string
        }
      ))
    }
  ))
  default = []
}

variable "service_directory_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      namespace = list(object(
        {
          namespace_url = string
        }
      ))
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
resource "google_dns_managed_zone" "this" {
  description    = var.description
  dns_name       = var.dns_name
  force_destroy  = var.force_destroy
  labels         = var.labels
  name           = var.name
  project        = var.project
  reverse_lookup = var.reverse_lookup
  visibility     = var.visibility

  dynamic "dnssec_config" {
    for_each = var.dnssec_config
    content {
      kind          = dnssec_config.value["kind"]
      non_existence = dnssec_config.value["non_existence"]
      state         = dnssec_config.value["state"]

      dynamic "default_key_specs" {
        for_each = dnssec_config.value.default_key_specs
        content {
          algorithm  = default_key_specs.value["algorithm"]
          key_length = default_key_specs.value["key_length"]
          key_type   = default_key_specs.value["key_type"]
          kind       = default_key_specs.value["kind"]
        }
      }

    }
  }

  dynamic "forwarding_config" {
    for_each = var.forwarding_config
    content {

      dynamic "target_name_servers" {
        for_each = forwarding_config.value.target_name_servers
        content {
          forwarding_path = target_name_servers.value["forwarding_path"]
          ipv4_address    = target_name_servers.value["ipv4_address"]
        }
      }

    }
  }

  dynamic "peering_config" {
    for_each = var.peering_config
    content {

      dynamic "target_network" {
        for_each = peering_config.value.target_network
        content {
          network_url = target_network.value["network_url"]
        }
      }

    }
  }

  dynamic "private_visibility_config" {
    for_each = var.private_visibility_config
    content {

      dynamic "networks" {
        for_each = private_visibility_config.value.networks
        content {
          network_url = networks.value["network_url"]
        }
      }

    }
  }

  dynamic "service_directory_config" {
    for_each = var.service_directory_config
    content {

      dynamic "namespace" {
        for_each = service_directory_config.value.namespace
        content {
          namespace_url = namespace.value["namespace_url"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
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
  value       = google_dns_managed_zone.this.id
}

output "name_servers" {
  description = "returns a list of string"
  value       = google_dns_managed_zone.this.name_servers
}

output "project" {
  description = "returns a string"
  value       = google_dns_managed_zone.this.project
}

output "this" {
  value = google_dns_managed_zone.this
}
```

[top](#index)