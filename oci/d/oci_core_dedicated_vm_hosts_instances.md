# oci_core_dedicated_vm_hosts_instances

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
module "oci_core_dedicated_vm_hosts_instances" {
  source = "./modules/oci/d/oci_core_dedicated_vm_hosts_instances"

  # availability_domain - (optional) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # dedicated_vm_host_id - (required) is a type of string
  dedicated_vm_host_id = null

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

variable "dedicated_vm_host_id" {
  description = "(required)"
  type        = string
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
data "oci_core_dedicated_vm_hosts_instances" "this" {
  availability_domain  = var.availability_domain
  compartment_id       = var.compartment_id
  dedicated_vm_host_id = var.dedicated_vm_host_id

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
output "dedicated_vm_host_instances" {
  description = "returns a list of object"
  value       = data.oci_core_dedicated_vm_hosts_instances.this.dedicated_vm_host_instances
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_dedicated_vm_hosts_instances.this.id
}

output "this" {
  value = oci_core_dedicated_vm_hosts_instances.this
}
```

[top](#index)