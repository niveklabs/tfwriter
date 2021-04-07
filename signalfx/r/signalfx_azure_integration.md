# signalfx_azure_integration

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
module "signalfx_azure_integration" {
  source = "./modules/signalfx/r/signalfx_azure_integration"

  # app_id - (required) is a type of string
  app_id = null
  # enabled - (required) is a type of bool
  enabled = null
  # environment - (optional) is a type of string
  environment = null
  # name - (required) is a type of string
  name = null
  # named_token - (optional) is a type of string
  named_token = null
  # poll_rate - (optional) is a type of number
  poll_rate = null
  # secret_key - (required) is a type of string
  secret_key = null
  # services - (required) is a type of set of string
  services = []
  # subscriptions - (required) is a type of set of string
  subscriptions = []
  # sync_guest_os_namespaces - (optional) is a type of bool
  sync_guest_os_namespaces = null
  # tenant_id - (required) is a type of string
  tenant_id = null

  custom_namespaces_per_service = [{
    namespaces = []
    service    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "app_id" {
  description = "(required) - Azure application ID for the SignalFx app."
  type        = string
}

variable "enabled" {
  description = "(required) - Whether the integration is enabled or not"
  type        = bool
}

variable "environment" {
  description = "(optional) - what type of Azure integration this is. The allowed values are `\"azure_us_government\"` and `\"azure\"`. Defaults to `\"azure\"`"
  type        = string
  default     = null
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
  description = "(optional) - Azure poll rate (in seconds). One of `60` or `300`."
  type        = number
  default     = null
}

variable "secret_key" {
  description = "(required) - Azure secret key that associates the SignalFx app in Azure with the Azure tenant."
  type        = string
}

variable "services" {
  description = "(required) - List of Microsoft Azure service names for the Azure services you want SignalFx to monitor. SignalFx only supports certain services, and if you specify an unsupported one, you receive an API error."
  type        = set(string)
}

variable "subscriptions" {
  description = "(required) - List of Azure subscriptions that SignalFx should monitor."
  type        = set(string)
}

variable "sync_guest_os_namespaces" {
  description = "(optional) - If enabled, SignalFx will try to sync additional namespaces for VMs (including VMs in scale sets): telegraf/mem, telegraf/cpu, azure.vm.windows.guest (these are namespaces recommended by Azure when enabling their Diagnostic Extension). If there are no metrics there, no new datapoints will be ingested."
  type        = bool
  default     = null
}

variable "tenant_id" {
  description = "(required) - Azure ID of the Azure tenant."
  type        = string
}

variable "custom_namespaces_per_service" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      namespaces = set(string)
      service    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "signalfx_azure_integration" "this" {
  # app_id - (required) is a type of string
  app_id = var.app_id
  # enabled - (required) is a type of bool
  enabled = var.enabled
  # environment - (optional) is a type of string
  environment = var.environment
  # name - (required) is a type of string
  name = var.name
  # named_token - (optional) is a type of string
  named_token = var.named_token
  # poll_rate - (optional) is a type of number
  poll_rate = var.poll_rate
  # secret_key - (required) is a type of string
  secret_key = var.secret_key
  # services - (required) is a type of set of string
  services = var.services
  # subscriptions - (required) is a type of set of string
  subscriptions = var.subscriptions
  # sync_guest_os_namespaces - (optional) is a type of bool
  sync_guest_os_namespaces = var.sync_guest_os_namespaces
  # tenant_id - (required) is a type of string
  tenant_id = var.tenant_id

  dynamic "custom_namespaces_per_service" {
    for_each = var.custom_namespaces_per_service
    content {
      # namespaces - (required) is a type of set of string
      namespaces = custom_namespaces_per_service.value["namespaces"]
      # service - (required) is a type of string
      service = custom_namespaces_per_service.value["service"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = signalfx_azure_integration.this.id
}

output "this" {
  value = signalfx_azure_integration.this
}
```

[top](#index)