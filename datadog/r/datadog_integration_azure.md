# datadog_integration_azure

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
module "datadog_integration_azure" {
  source = "./modules/datadog/r/datadog_integration_azure"

  # client_id - (required) is a type of string
  client_id = null
  # client_secret - (required) is a type of string
  client_secret = null
  # host_filters - (optional) is a type of string
  host_filters = null
  # tenant_name - (required) is a type of string
  tenant_name = null
}
```

[top](#index)

### Variables

```terraform
variable "client_id" {
  description = "(required) - Your Azure web application ID."
  type        = string
}

variable "client_secret" {
  description = "(required) - (Required for Initial Creation) Your Azure web application secret key."
  type        = string
}

variable "host_filters" {
  description = "(optional) - String of host tag(s) (in the form `key:value,key:value`) defines a filter that Datadog will use when collecting metrics from Azure. Limit the Azure instances that are pulled into Datadog by using tags. Only hosts that match one of the defined tags are imported into Datadog. e.x. `env:production,deploymentgroup:red`"
  type        = string
  default     = null
}

variable "tenant_name" {
  description = "(required) - Your Azure Active Directory ID."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "datadog_integration_azure" "this" {
  # client_id - (required) is a type of string
  client_id = var.client_id
  # client_secret - (required) is a type of string
  client_secret = var.client_secret
  # host_filters - (optional) is a type of string
  host_filters = var.host_filters
  # tenant_name - (required) is a type of string
  tenant_name = var.tenant_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_integration_azure.this.id
}

output "this" {
  value = datadog_integration_azure.this
}
```

[top](#index)