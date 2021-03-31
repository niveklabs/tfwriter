# azuredevops_variable_group

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
    azuredevops = ">= 0.1.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuredevops_variable_group" {
  source = "./modules/azuredevops/r/azuredevops_variable_group"

  # allow_access - (optional) is a type of bool
  allow_access = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null

  key_vault = [{
    name                = null
    service_endpoint_id = null
  }]

  variable = [{
    content_type = null
    enabled      = null
    expires      = null
    is_secret    = null
    name         = null
    secret_value = null
    value        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allow_access" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "key_vault" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      name                = string
      service_endpoint_id = string
    }
  ))
  default = []
}

variable "variable" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      content_type = string
      enabled      = bool
      expires      = string
      is_secret    = bool
      name         = string
      secret_value = string
      value        = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_variable_group" "this" {
  allow_access = var.allow_access
  description  = var.description
  name         = var.name
  project_id   = var.project_id

  dynamic "key_vault" {
    for_each = var.key_vault
    content {
      name                = key_vault.value["name"]
      service_endpoint_id = key_vault.value["service_endpoint_id"]
    }
  }

  dynamic "variable" {
    for_each = var.variable
    content {
      is_secret    = variable.value["is_secret"]
      name         = variable.value["name"]
      secret_value = variable.value["secret_value"]
      value        = variable.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azuredevops_variable_group.this.id
}

output "this" {
  value = azuredevops_variable_group.this
}
```

[top](#index)