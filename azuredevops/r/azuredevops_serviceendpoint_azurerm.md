# azuredevops_serviceendpoint_azurerm

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
module "azuredevops_serviceendpoint_azurerm" {
  source = "./modules/azuredevops/r/azuredevops_serviceendpoint_azurerm"

  # authorization - (optional) is a type of map of string
  authorization = {}
  # azurerm_spn_tenantid - (required) is a type of string
  azurerm_spn_tenantid = null
  # azurerm_subscription_id - (required) is a type of string
  azurerm_subscription_id = null
  # azurerm_subscription_name - (required) is a type of string
  azurerm_subscription_name = null
  # description - (optional) is a type of string
  description = null
  # project_id - (required) is a type of string
  project_id = null
  # resource_group - (optional) is a type of string
  resource_group = null
  # service_endpoint_name - (required) is a type of string
  service_endpoint_name = null

  credentials = [{
    serviceprincipalid       = null
    serviceprincipalkey      = null
    serviceprincipalkey_hash = null
  }]
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

variable "azurerm_spn_tenantid" {
  description = "(required) - The service principal tenant id which should be used."
  type        = string
}

variable "azurerm_subscription_id" {
  description = "(required) - The Azure subscription Id which should be used."
  type        = string
}

variable "azurerm_subscription_name" {
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
  description = "(optional) - Scope Resource Group"
  type        = string
  default     = null
}

variable "service_endpoint_name" {
  description = "(required)"
  type        = string
}

variable "credentials" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      serviceprincipalid       = string
      serviceprincipalkey      = string
      serviceprincipalkey_hash = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_serviceendpoint_azurerm" "this" {
  authorization             = var.authorization
  azurerm_spn_tenantid      = var.azurerm_spn_tenantid
  azurerm_subscription_id   = var.azurerm_subscription_id
  azurerm_subscription_name = var.azurerm_subscription_name
  description               = var.description
  project_id                = var.project_id
  resource_group            = var.resource_group
  service_endpoint_name     = var.service_endpoint_name

  dynamic "credentials" {
    for_each = var.credentials
    content {
      serviceprincipalid  = credentials.value["serviceprincipalid"]
      serviceprincipalkey = credentials.value["serviceprincipalkey"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "authorization" {
  description = "returns a map of string"
  value       = azuredevops_serviceendpoint_azurerm.this.authorization
}

output "id" {
  description = "returns a string"
  value       = azuredevops_serviceendpoint_azurerm.this.id
}

output "this" {
  value = azuredevops_serviceendpoint_azurerm.this
}
```

[top](#index)