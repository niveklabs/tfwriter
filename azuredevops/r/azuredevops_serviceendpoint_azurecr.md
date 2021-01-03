# azuredevops_serviceendpoint_azurecr

[back](../azuredevops.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azuredevops = ">= 0.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuredevops_serviceendpoint_azurecr" {
  source = "./modules/azuredevops/r/azuredevops_serviceendpoint_azurecr"

  # authorization - (optional) is a type of map of string
  authorization = {}
  # azurecr_name - (required) is a type of string
  azurecr_name = null
  # azurecr_spn_tenantid - (required) is a type of string
  azurecr_spn_tenantid = null
  # azurecr_subscription_id - (required) is a type of string
  azurecr_subscription_id = null
  # azurecr_subscription_name - (required) is a type of string
  azurecr_subscription_name = null
  # description - (optional) is a type of string
  description = null
  # project_id - (required) is a type of string
  project_id = null
  # resource_group - (required) is a type of string
  resource_group = null
  # service_endpoint_name - (required) is a type of string
  service_endpoint_name = null
}
```

[top](#index)

### Variables

```terraform
variable "authorization" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "azurecr_name" {
  description = "(required) - The AzureContainerRegistry registry which should be used."
  type        = string
}

variable "azurecr_spn_tenantid" {
  description = "(required) - The service principal tenant id which should be used."
  type        = string
}

variable "azurecr_subscription_id" {
  description = "(required) - The Azure subscription Id which should be used."
  type        = string
}

variable "azurecr_subscription_name" {
  description = "(required) - The Azure subscription name which should be used."
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "resource_group" {
  description = "(required) - Scope Resource Group"
  type        = string
}

variable "service_endpoint_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_serviceendpoint_azurecr" "this" {
  authorization             = var.authorization
  azurecr_name              = var.azurecr_name
  azurecr_spn_tenantid      = var.azurecr_spn_tenantid
  azurecr_subscription_id   = var.azurecr_subscription_id
  azurecr_subscription_name = var.azurecr_subscription_name
  description               = var.description
  project_id                = var.project_id
  resource_group            = var.resource_group
  service_endpoint_name     = var.service_endpoint_name
}
```

[top](#index)

### Outputs

```terraform
output "authorization" {
  description = "returns a map of string"
  value       = azuredevops_serviceendpoint_azurecr.this.authorization
}

output "id" {
  description = "returns a string"
  value       = azuredevops_serviceendpoint_azurecr.this.id
}

output "this" {
  value = azuredevops_serviceendpoint_azurecr.this
}
```

[top](#index)