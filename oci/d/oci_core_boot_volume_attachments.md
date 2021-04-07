# oci_core_boot_volume_attachments

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
module "oci_core_boot_volume_attachments" {
  source = "./modules/oci/d/oci_core_boot_volume_attachments"

  # availability_domain - (required) is a type of string
  availability_domain = null
  # boot_volume_id - (optional) is a type of string
  boot_volume_id = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # instance_id - (optional) is a type of string
  instance_id = null

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
  description = "(required)"
  type        = string
}

variable "boot_volume_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "instance_id" {
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
data "oci_core_boot_volume_attachments" "this" {
  availability_domain = var.availability_domain
  boot_volume_id      = var.boot_volume_id
  compartment_id      = var.compartment_id
  instance_id         = var.instance_id

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
output "boot_volume_attachments" {
  description = "returns a list of object"
  value       = data.oci_core_boot_volume_attachments.this.boot_volume_attachments
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_boot_volume_attachments.this.id
}

output "this" {
  value = oci_core_boot_volume_attachments.this
}
```

[top](#index)