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
    datadog = ">= 2.24.0"
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
  description = "(optional) - Your PagerDuty API token."
  type        = string
  default     = null
}

variable "individual_services" {
  description = "(optional) - Boolean to specify whether or not individual service objects specified by [datadog_integration_pagerduty_service_object](https://registry.terraform.io/providers/DataDog/datadog/latest/docs/resources/integration_pagerduty_service_object) resource are to be used. Mutually exclusive with `services` key."
  type        = bool
  default     = null
}

variable "schedules" {
  description = "(optional) - Array of your schedule URLs."
  type        = list(string)
  default     = null
}

variable "subdomain" {
  description = "(required) - Your PagerDuty account’s personalized subdomain name."
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