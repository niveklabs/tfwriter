# oci_computeinstanceagent_instance_agent_plugins

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
module "oci_computeinstanceagent_instance_agent_plugins" {
  source = "./modules/oci/d/oci_computeinstanceagent_instance_agent_plugins"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # instanceagent_id - (required) is a type of string
  instanceagent_id = null
  # name - (optional) is a type of string
  name = null
  # status - (optional) is a type of string
  status = null

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

variable "instanceagent_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
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
data "oci_computeinstanceagent_instance_agent_plugins" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # instanceagent_id - (required) is a type of string
  instanceagent_id = var.instanceagent_id
  # name - (optional) is a type of string
  name = var.name
  # status - (optional) is a type of string
  status = var.status

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
  value       = data.oci_computeinstanceagent_instance_agent_plugins.this.id
}

output "instance_agent_plugins" {
  description = "returns a list of object"
  value       = data.oci_computeinstanceagent_instance_agent_plugins.this.instance_agent_plugins
}

output "this" {
  value = oci_computeinstanceagent_instance_agent_plugins.this
}
```

[top](#index)