# oci_management_agent_management_agents

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_management_agent_management_agents" {
  source = "./modules/oci/d/oci_management_agent_management_agents"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # platform_type - (optional) is a type of string
  platform_type = null
  # plugin_name - (optional) is a type of string
  plugin_name = null
  # state - (optional) is a type of string
  state = null
  # version - (optional) is a type of string
  version = null

  filter = [{
    name   = null
    regex  = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "platform_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "plugin_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      regex  = bool
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "oci_management_agent_management_agents" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # platform_type - (optional) is a type of string
  platform_type = var.platform_type
  # plugin_name - (optional) is a type of string
  plugin_name = var.plugin_name
  # state - (optional) is a type of string
  state = var.state
  # version - (optional) is a type of string
  version = var.version

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # regex - (optional) is a type of bool
      regex = filter.value["regex"]
      # values - (required) is a type of list of string
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agents.this.id
}

output "management_agents" {
  description = "returns a list of object"
  value       = data.oci_management_agent_management_agents.this.management_agents
}

output "this" {
  value = oci_management_agent_management_agents.this
}
```

[top](#index)