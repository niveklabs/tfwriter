# oci_core_dedicated_vm_hosts

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_dedicated_vm_hosts" {
  source = "./modules/oci/d/oci_core_dedicated_vm_hosts"

  # availability_domain - (optional) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # instance_shape_name - (optional) is a type of string
  instance_shape_name = null
  # state - (optional) is a type of string
  state = null

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
variable "availability_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_shape_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
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
data "oci_core_dedicated_vm_hosts" "this" {
  availability_domain = var.availability_domain
  compartment_id      = var.compartment_id
  display_name        = var.display_name
  instance_shape_name = var.instance_shape_name
  state               = var.state

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      regex  = filter.value["regex"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "dedicated_vm_hosts" {
  description = "returns a list of object"
  value       = data.oci_core_dedicated_vm_hosts.this.dedicated_vm_hosts
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_dedicated_vm_hosts.this.id
}

output "this" {
  value = oci_core_dedicated_vm_hosts.this
}
```

[top](#index)