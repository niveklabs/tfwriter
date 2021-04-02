# bigip_sys_iapp

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_sys_iapp" {
  source = "./modules/bigip/r/bigip_sys_iapp"

  # description - (optional) is a type of string
  description = null
  # devicegroup - (optional) is a type of string
  devicegroup = null
  # execute_action - (optional) is a type of string
  execute_action = null
  # inherited_devicegroup - (optional) is a type of string
  inherited_devicegroup = null
  # inherited_traffic_group - (optional) is a type of string
  inherited_traffic_group = null
  # jsonfile - (optional) is a type of string
  jsonfile = null
  # name - (optional) is a type of string
  name = null
  # partition - (optional) is a type of string
  partition = null
  # strict_updates - (optional) is a type of string
  strict_updates = null
  # template - (optional) is a type of string
  template = null
  # template_modified - (optional) is a type of string
  template_modified = null
  # template_prerequisite_errors - (optional) is a type of string
  template_prerequisite_errors = null
  # traffic_group - (optional) is a type of string
  traffic_group = null

  lists = [{
    encrypted = null
    value     = null
  }]

  metadata = [{
    persists = null
    value    = null
  }]

  tables = [{
    column_names      = []
    encrypted_columns = null
    name              = null
    rows = [{
      row = []
    }]
  }]

  variables = [{
    encrypted = null
    name      = null
    value     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Address of the Iapp which needs to be Iappensed"
  type        = string
  default     = null
}

variable "devicegroup" {
  description = "(optional) - BIG-IP password"
  type        = string
  default     = null
}

variable "execute_action" {
  description = "(optional) - BIG-IP password"
  type        = string
  default     = null
}

variable "inherited_devicegroup" {
  description = "(optional) - BIG-IP password"
  type        = string
  default     = null
}

variable "inherited_traffic_group" {
  description = "(optional) - BIG-IP password"
  type        = string
  default     = null
}

variable "jsonfile" {
  description = "(optional) - Address of the Iapp which needs to be Iappensed"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Address of the Iapp which needs to be Iappensed"
  type        = string
  default     = null
}

variable "partition" {
  description = "(optional) - Address of the Iapp which needs to be Iappensed"
  type        = string
  default     = null
}

variable "strict_updates" {
  description = "(optional) - BIG-IP password"
  type        = string
  default     = null
}

variable "template" {
  description = "(optional) - BIG-IP password"
  type        = string
  default     = null
}

variable "template_modified" {
  description = "(optional) - BIG-IP password"
  type        = string
  default     = null
}

variable "template_prerequisite_errors" {
  description = "(optional) - BIG-IP password"
  type        = string
  default     = null
}

variable "traffic_group" {
  description = "(optional) - BIG-IP password"
  type        = string
  default     = null
}

variable "lists" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      encrypted = string
      value     = string
    }
  ))
  default = []
}

variable "metadata" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      persists = string
      value    = string
    }
  ))
  default = []
}

variable "tables" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      column_names      = list(string)
      encrypted_columns = string
      name              = string
      rows = list(object(
        {
          row = list(string)
        }
      ))
    }
  ))
  default = []
}

variable "variables" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      encrypted = string
      name      = string
      value     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "bigip_sys_iapp" "this" {
  description                  = var.description
  devicegroup                  = var.devicegroup
  execute_action               = var.execute_action
  inherited_devicegroup        = var.inherited_devicegroup
  inherited_traffic_group      = var.inherited_traffic_group
  jsonfile                     = var.jsonfile
  name                         = var.name
  partition                    = var.partition
  strict_updates               = var.strict_updates
  template                     = var.template
  template_modified            = var.template_modified
  template_prerequisite_errors = var.template_prerequisite_errors
  traffic_group                = var.traffic_group

  dynamic "lists" {
    for_each = var.lists
    content {
      encrypted = lists.value["encrypted"]
      value     = lists.value["value"]
    }
  }

  dynamic "metadata" {
    for_each = var.metadata
    content {
      persists = metadata.value["persists"]
      value    = metadata.value["value"]
    }
  }

  dynamic "tables" {
    for_each = var.tables
    content {
      column_names      = tables.value["column_names"]
      encrypted_columns = tables.value["encrypted_columns"]
      name              = tables.value["name"]

      dynamic "rows" {
        for_each = tables.value.rows
        content {
          row = rows.value["row"]
        }
      }

    }
  }

  dynamic "variables" {
    for_each = var.variables
    content {
      encrypted = variables.value["encrypted"]
      name      = variables.value["name"]
      value     = variables.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_sys_iapp.this.id
}

output "this" {
  value = bigip_sys_iapp.this
}
```

[top](#index)