# datadog_integration_pagerduty

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.18.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_integration_pagerduty" {
  source = "./modules/datadog/r/datadog_integration_pagerduty"

  # api_token - (optional) is a type of string
  api_token = null
  # individual_services - (optional) is a type of bool
  individual_services = null
  # schedules - (optional) is a type of list of string
  schedules = []
  # subdomain - (required) is a type of string
  subdomain = null

  services = [{
    service_key  = null
    service_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "api_token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "individual_services" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "schedules" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "subdomain" {
  description = "(required)"
  type        = string
}

variable "services" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      service_key  = string
      service_name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "datadog_integration_pagerduty" "this" {
  api_token           = var.api_token
  individual_services = var.individual_services
  schedules           = var.schedules
  subdomain           = var.subdomain

  dynamic "services" {
    for_each = var.services
    content {
      service_key  = services.value["service_key"]
      service_name = services.value["service_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_integration_pagerduty.this.id
}

output "this" {
  value = datadog_integration_pagerduty.this
}
```

[top](#index)