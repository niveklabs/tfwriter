# google_apigee_organization

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
module "google_apigee_organization" {
  source = "./modules/google-beta/r/google_apigee_organization"

  # analytics_region - (optional) is a type of string
  analytics_region = null
  # authorized_network - (optional) is a type of string
  authorized_network = null
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # project_id - (required) is a type of string
  project_id = null
  # runtime_database_encryption_key_name - (optional) is a type of string
  runtime_database_encryption_key_name = null
  # runtime_type - (optional) is a type of string
  runtime_type = null

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
variable "analytics_region" {
  description = "(optional) - Primary GCP region for analytics data storage. For valid values, see [Create an Apigee organization](https://cloud.google.com/apigee/docs/api-platform/get-started/create-org)."
  type        = string
  default     = null
}

variable "authorized_network" {
  description = "(optional) - Compute Engine network used for Service Networking to be peered with Apigee runtime instances.\nSee [Getting started with the Service Networking API](https://cloud.google.com/service-infrastructure/docs/service-networking/getting-started).\nValid only when 'RuntimeType' is set to CLOUD. The value can be updated only when there are no runtime instances. For example: \"default\"."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Description of the Apigee organization."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of the Apigee organization."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required) - The project ID associated with the Apigee organization."
  type        = string
}

variable "runtime_database_encryption_key_name" {
  description = "(optional) - Cloud KMS key name used for encrypting the data that is stored and replicated across runtime instances.\nUpdate is not allowed after the organization is created.\nIf not specified, a Google-Managed encryption key will be used.\nValid only when 'RuntimeType' is CLOUD. For example: 'projects/foo/locations/us/keyRings/bar/cryptoKeys/baz'."
  type        = string
  default     = null
}

variable "runtime_type" {
  description = "(optional) - Runtime type of the Apigee organization based on the Apigee subscription purchased. Default value: \"CLOUD\" Possible values: [\"CLOUD\", \"HYBRID\"]"
  type        = string
  default     = null
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
resource "google_apigee_organization" "this" {
  analytics_region                     = var.analytics_region
  authorized_network                   = var.authorized_network
  description                          = var.description
  display_name                         = var.display_name
  project_id                           = var.project_id
  runtime_database_encryption_key_name = var.runtime_database_encryption_key_name
  runtime_type                         = var.runtime_type

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
output "ca_certificate" {
  description = "returns a string"
  value       = google_apigee_organization.this.ca_certificate
}

output "id" {
  description = "returns a string"
  value       = google_apigee_organization.this.id
}

output "name" {
  description = "returns a string"
  value       = google_apigee_organization.this.name
}

output "subscription_type" {
  description = "returns a string"
  value       = google_apigee_organization.this.subscription_type
}

output "this" {
  value = google_apigee_organization.this
}
```

[top](#index)