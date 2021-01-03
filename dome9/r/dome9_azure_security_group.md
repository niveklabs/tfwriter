# dome9_azure_security_group

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.20.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_azure_security_group" {
  source = "./modules/dome9/r/dome9_azure_security_group"

  # description - (optional) is a type of string
  description = null
  # dome9_cloud_account_id - (required) is a type of string
  dome9_cloud_account_id = null
  # dome9_security_group_name - (required) is a type of string
  dome9_security_group_name = null
  # is_tamper_protected - (optional) is a type of bool
  is_tamper_protected = null
  # region - (required) is a type of string
  region = null
  # resource_group - (required) is a type of string
  resource_group = null

  inbound = [{
    access                  = null
    description             = null
    destination_port_ranges = []
    destination_scopes = [{
      data = {}
      type = null
    }]
    direction          = null
    is_default         = null
    name               = null
    priority           = null
    protocol           = null
    source_port_ranges = []
    source_scopes = [{
      data = {}
      type = null
    }]
  }]

  outbound = [{
    access                  = null
    description             = null
    destination_port_ranges = []
    destination_scopes = [{
      data = {}
      type = null
    }]
    direction          = null
    is_default         = null
    name               = null
    priority           = null
    protocol           = null
    source_port_ranges = []
    source_scopes = [{
      data = {}
      type = null
    }]
  }]

  tags = [{
    key   = null
    value = null
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

variable "dome9_cloud_account_id" {
  description = "(required)"
  type        = string
}

variable "dome9_security_group_name" {
  description = "(required)"
  type        = string
}

variable "is_tamper_protected" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "resource_group" {
  description = "(required)"
  type        = string
}

variable "inbound" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access                  = string
      description             = string
      destination_port_ranges = list(string)
      destination_scopes = list(object(
        {
          data = map(string)
          type = string
        }
      ))
      direction          = string
      is_default         = bool
      name               = string
      priority           = number
      protocol           = string
      source_port_ranges = list(string)
      source_scopes = list(object(
        {
          data = map(string)
          type = string
        }
      ))
    }
  ))
  default = []
}

variable "outbound" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access                  = string
      description             = string
      destination_port_ranges = list(string)
      destination_scopes = list(object(
        {
          data = map(string)
          type = string
        }
      ))
      direction          = string
      is_default         = bool
      name               = string
      priority           = number
      protocol           = string
      source_port_ranges = list(string)
      source_scopes = list(object(
        {
          data = map(string)
          type = string
        }
      ))
    }
  ))
  default = []
}

variable "tags" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "dome9_azure_security_group" "this" {
  description               = var.description
  dome9_cloud_account_id    = var.dome9_cloud_account_id
  dome9_security_group_name = var.dome9_security_group_name
  is_tamper_protected       = var.is_tamper_protected
  region                    = var.region
  resource_group            = var.resource_group

  dynamic "inbound" {
    for_each = var.inbound
    content {
      access                  = inbound.value["access"]
      description             = inbound.value["description"]
      destination_port_ranges = inbound.value["destination_port_ranges"]
      is_default              = inbound.value["is_default"]
      name                    = inbound.value["name"]
      priority                = inbound.value["priority"]
      protocol                = inbound.value["protocol"]
      source_port_ranges      = inbound.value["source_port_ranges"]

      dynamic "destination_scopes" {
        for_each = inbound.value.destination_scopes
        content {
          data = destination_scopes.value["data"]
          type = destination_scopes.value["type"]
        }
      }

      dynamic "source_scopes" {
        for_each = inbound.value.source_scopes
        content {
          data = source_scopes.value["data"]
          type = source_scopes.value["type"]
        }
      }

    }
  }

  dynamic "outbound" {
    for_each = var.outbound
    content {
      access                  = outbound.value["access"]
      description             = outbound.value["description"]
      destination_port_ranges = outbound.value["destination_port_ranges"]
      is_default              = outbound.value["is_default"]
      name                    = outbound.value["name"]
      priority                = outbound.value["priority"]
      protocol                = outbound.value["protocol"]
      source_port_ranges      = outbound.value["source_port_ranges"]

      dynamic "destination_scopes" {
        for_each = outbound.value.destination_scopes
        content {
          data = destination_scopes.value["data"]
          type = destination_scopes.value["type"]
        }
      }

      dynamic "source_scopes" {
        for_each = outbound.value.source_scopes
        content {
          data = source_scopes.value["data"]
          type = source_scopes.value["type"]
        }
      }

    }
  }

  dynamic "tags" {
    for_each = var.tags
    content {
      key   = tags.value["key"]
      value = tags.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cloud_account_name" {
  description = "returns a string"
  value       = dome9_azure_security_group.this.cloud_account_name
}

output "external_security_group_id" {
  description = "returns a string"
  value       = dome9_azure_security_group.this.external_security_group_id
}

output "id" {
  description = "returns a string"
  value       = dome9_azure_security_group.this.id
}

output "last_updated_by_dome9" {
  description = "returns a string"
  value       = dome9_azure_security_group.this.last_updated_by_dome9
}

output "this" {
  value = dome9_azure_security_group.this
}
```

[top](#index)