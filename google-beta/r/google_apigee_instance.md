# google_apigee_instance

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
module "google_apigee_instance" {
  source = "./modules/google-beta/r/google_apigee_instance"

  # description - (optional) is a type of string
  description = null
  # disk_encryption_key_name - (optional) is a type of string
  disk_encryption_key_name = null
  # display_name - (optional) is a type of string
  display_name = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # org_id - (required) is a type of string
  org_id = null
  # peering_cidr_range - (optional) is a type of string
  peering_cidr_range = null

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
  description = "(optional) - Description of the instance."
  type        = string
  default     = null
}

variable "disk_encryption_key_name" {
  description = "(optional) - Customer Managed Encryption Key (CMEK) used for disk and volume encryption. Required for Apigee paid subscriptions only.\nUse the following format: 'projects/([^/]+)/locations/([^/]+)/keyRings/([^/]+)/cryptoKeys/([^/]+)'"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - Display name of the instance."
  type        = string
  default     = null
}

variable "location" {
  description = "(required) - Compute Engine location where the instance resides. For trial organization\nsubscriptions, the location must be a Compute Engine zone. For paid organization\nsubscriptions, it should correspond to a Compute Engine region."
  type        = string
}

variable "name" {
  description = "(required) - Resource ID of the instance."
  type        = string
}

variable "org_id" {
  description = "(required) - The Apigee Organization associated with the Apigee instance,\nin the format 'organizations/{{org_name}}'."
  type        = string
}

variable "peering_cidr_range" {
  description = "(optional) - The size of the CIDR block range that will be reserved by the instance. Possible values: [\"SLASH_16\", \"SLASH_20\"]"
  type        = string
  default     = null
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
resource "google_apigee_instance" "this" {
  description              = var.description
  disk_encryption_key_name = var.disk_encryption_key_name
  display_name             = var.display_name
  location                 = var.location
  name                     = var.name
  org_id                   = var.org_id
  peering_cidr_range       = var.peering_cidr_range

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
output "host" {
  description = "returns a string"
  value       = google_apigee_instance.this.host
}

output "id" {
  description = "returns a string"
  value       = google_apigee_instance.this.id
}

output "port" {
  description = "returns a string"
  value       = google_apigee_instance.this.port
}

output "this" {
  value = google_apigee_instance.this
}
```

[top](#index)