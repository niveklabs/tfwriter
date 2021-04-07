# opsgenie_incident_template

[back](../opsgenie.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opsgenie = ">= 0.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opsgenie_incident_template" {
  source = "./modules/opsgenie/r/opsgenie_incident_template"

  # description - (optional) is a type of string
  description = null
  # details - (optional) is a type of map of string
  details = {}
  # impacted_services - (optional) is a type of set of string
  impacted_services = []
  # message - (required) is a type of string
  message = null
  # name - (required) is a type of string
  name = null
  # priority - (required) is a type of string
  priority = null
  # tags - (optional) is a type of set of string
  tags = []

  stakeholder_properties = [{
    description = null
    enable      = null
    message     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "details" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "impacted_services" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "message" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "priority" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "stakeholder_properties" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      description = string
      enable      = bool
      message     = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "opsgenie_incident_template" "this" {
  # description - (optional) is a type of string
  description = var.description
  # details - (optional) is a type of map of string
  details = var.details
  # impacted_services - (optional) is a type of set of string
  impacted_services = var.impacted_services
  # message - (required) is a type of string
  message = var.message
  # name - (required) is a type of string
  name = var.name
  # priority - (required) is a type of string
  priority = var.priority
  # tags - (optional) is a type of set of string
  tags = var.tags

  dynamic "stakeholder_properties" {
    for_each = var.stakeholder_properties
    content {
      # description - (optional) is a type of string
      description = stakeholder_properties.value["description"]
      # enable - (optional) is a type of bool
      enable = stakeholder_properties.value["enable"]
      # message - (required) is a type of string
      message = stakeholder_properties.value["message"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opsgenie_incident_template.this.id
}

output "this" {
  value = opsgenie_incident_template.this
}
```

[top](#index)