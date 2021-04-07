# signalfx_gcp_integration

[back](../signalfx.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    signalfx = ">= 6.7.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "signalfx_gcp_integration" {
  source = "./modules/signalfx/r/signalfx_gcp_integration"

  # enabled - (required) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # named_token - (optional) is a type of string
  named_token = null
  # poll_rate - (optional) is a type of number
  poll_rate = null
  # services - (optional) is a type of set of string
  services = []
  # whitelist - (optional) is a type of set of string
  whitelist = []

  project_service_keys = [{
    project_id  = null
    project_key = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(required) - Whether the integration is enabled or not"
  type        = bool
}

variable "name" {
  description = "(required) - Name of the integration"
  type        = string
}

variable "named_token" {
  description = "(optional) - A named token to use for ingest"
  type        = string
  default     = null
}

variable "poll_rate" {
  description = "(optional) - GCP poll rate"
  type        = number
  default     = null
}

variable "services" {
  description = "(optional) - GCP enabled services"
  type        = set(string)
  default     = null
}

variable "whitelist" {
  description = "(optional) - Compute Metadata Whitelist"
  type        = set(string)
  default     = null
}

variable "project_service_keys" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      project_id  = string
      project_key = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "signalfx_gcp_integration" "this" {
  # enabled - (required) is a type of bool
  enabled = var.enabled
  # name - (required) is a type of string
  name = var.name
  # named_token - (optional) is a type of string
  named_token = var.named_token
  # poll_rate - (optional) is a type of number
  poll_rate = var.poll_rate
  # services - (optional) is a type of set of string
  services = var.services
  # whitelist - (optional) is a type of set of string
  whitelist = var.whitelist

  dynamic "project_service_keys" {
    for_each = var.project_service_keys
    content {
      # project_id - (required) is a type of string
      project_id = project_service_keys.value["project_id"]
      # project_key - (required) is a type of string
      project_key = project_service_keys.value["project_key"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = signalfx_gcp_integration.this.id
}

output "this" {
  value = signalfx_gcp_integration.this
}
```

[top](#index)