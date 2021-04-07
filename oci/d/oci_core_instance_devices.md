# oci_core_instance_devices

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
module "oci_core_instance_devices" {
  source = "./modules/oci/d/oci_core_instance_devices"

  # instance_id - (required) is a type of string
  instance_id = null
  # is_available - (optional) is a type of bool
  is_available = null
  # name - (optional) is a type of string
  name = null

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
variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "is_available" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
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
data "oci_core_instance_devices" "this" {
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # is_available - (optional) is a type of bool
  is_available = var.is_available
  # name - (optional) is a type of string
  name = var.name

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
output "devices" {
  description = "returns a list of object"
  value       = data.oci_core_instance_devices.this.devices
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_instance_devices.this.id
}

output "this" {
  value = oci_core_instance_devices.this
}
```

[top](#index)