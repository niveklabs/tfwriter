# google_active_directory_domain

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
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_active_directory_domain" {
  source = "./modules/google-beta/r/google_active_directory_domain"

  # admin - (optional) is a type of string
  admin = null
  # authorized_networks - (optional) is a type of set of string
  authorized_networks = []
  # domain_name - (required) is a type of string
  domain_name = null
  # labels - (optional) is a type of map of string
  labels = {}
  # locations - (required) is a type of list of string
  locations = []
  # project - (optional) is a type of string
  project = null
  # reserved_ip_range - (required) is a type of string
  reserved_ip_range = null

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
variable "admin" {
  description = "(optional) - The name of delegated administrator account used to perform Active Directory operations. \nIf not specified, setupadmin will be used."
  type        = string
  default     = null
}

variable "authorized_networks" {
  description = "(optional) - The full names of the Google Compute Engine networks the domain instance is connected to. The domain is only available on networks listed in authorizedNetworks.\nIf CIDR subnets overlap between networks, domain creation will fail."
  type        = set(string)
  default     = null
}

variable "domain_name" {
  description = "(required) - The fully qualified domain name. e.g. mydomain.myorganization.com, with the restrictions, \nhttps://cloud.google.com/managed-microsoft-ad/reference/rest/v1/projects.locations.global.domains."
  type        = string
}

variable "labels" {
  description = "(optional) - Resource labels that can contain user-provided metadata"
  type        = map(string)
  default     = null
}

variable "locations" {
  description = "(required) - Locations where domain needs to be provisioned. [regions][compute/docs/regions-zones/] \ne.g. us-west1 or us-east4 Service supports up to 4 locations at once. Each location will use a /26 block."
  type        = list(string)
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reserved_ip_range" {
  description = "(required) - The CIDR range of internal addresses that are reserved for this domain. Reserved networks must be /24 or larger. \nRanges must be unique and non-overlapping with existing subnets in authorizedNetworks"
  type        = string
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
resource "google_active_directory_domain" "this" {
  admin               = var.admin
  authorized_networks = var.authorized_networks
  domain_name         = var.domain_name
  labels              = var.labels
  locations           = var.locations
  project             = var.project
  reserved_ip_range   = var.reserved_ip_range

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
output "fqdn" {
  description = "returns a string"
  value       = google_active_directory_domain.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = google_active_directory_domain.this.id
}

output "name" {
  description = "returns a string"
  value       = google_active_directory_domain.this.name
}

output "project" {
  description = "returns a string"
  value       = google_active_directory_domain.this.project
}

output "this" {
  value = google_active_directory_domain.this
}
```

[top](#index)