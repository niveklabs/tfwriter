# google_active_directory_domain_trust

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_active_directory_domain_trust" {
  source = "./modules/google/r/google_active_directory_domain_trust"

  # domain - (required) is a type of string
  domain = null
  # project - (optional) is a type of string
  project = null
  # selective_authentication - (optional) is a type of bool
  selective_authentication = null
  # target_dns_ip_addresses - (required) is a type of set of string
  target_dns_ip_addresses = []
  # target_domain_name - (required) is a type of string
  target_domain_name = null
  # trust_direction - (required) is a type of string
  trust_direction = null
  # trust_handshake_secret - (required) is a type of string
  trust_handshake_secret = null
  # trust_type - (required) is a type of string
  trust_type = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "domain" {
  description = "(required) - The fully qualified domain name. e.g. mydomain.myorganization.com, with the restrictions, \nhttps://cloud.google.com/managed-microsoft-ad/reference/rest/v1/projects.locations.global.domains."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "selective_authentication" {
  description = "(optional) - Whether the trusted side has forest/domain wide access or selective access to an approved set of resources."
  type        = bool
  default     = null
}

variable "target_dns_ip_addresses" {
  description = "(required) - The target DNS server IP addresses which can resolve the remote domain involved in the trust."
  type        = set(string)
}

variable "target_domain_name" {
  description = "(required) - The fully qualified target domain name which will be in trust with the current domain."
  type        = string
}

variable "trust_direction" {
  description = "(required) - The trust direction, which decides if the current domain is trusted, trusting, or both. Possible values: [\"INBOUND\", \"OUTBOUND\", \"BIDIRECTIONAL\"]"
  type        = string
}

variable "trust_handshake_secret" {
  description = "(required) - The trust secret used for the handshake with the target domain. This will not be stored."
  type        = string
}

variable "trust_type" {
  description = "(required) - The type of trust represented by the trust resource. Possible values: [\"FOREST\", \"EXTERNAL\"]"
  type        = string
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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

```hcl
resource "google_active_directory_domain_trust" "this" {
  domain                   = var.domain
  project                  = var.project
  selective_authentication = var.selective_authentication
  target_dns_ip_addresses  = var.target_dns_ip_addresses
  target_domain_name       = var.target_domain_name
  trust_direction          = var.trust_direction
  trust_handshake_secret   = var.trust_handshake_secret
  trust_type               = var.trust_type

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

```hcl
output "id" {
  description = "returns a string"
  value       = google_active_directory_domain_trust.this.id
}

output "project" {
  description = "returns a string"
  value       = google_active_directory_domain_trust.this.project
}

output "this" {
  value = google_active_directory_domain_trust.this
}
```

[top](#index)