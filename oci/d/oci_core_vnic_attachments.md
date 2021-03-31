# oci_core_vnic_attachments

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
module "oci_core_vnic_attachments" {
  source = "./modules/oci/d/oci_core_vnic_attachments"

  # availability_domain - (optional) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # instance_id - (optional) is a type of string
  instance_id = null
  # vnic_id - (optional) is a type of string
  vnic_id = null

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

variable "instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vnic_id" {
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
data "oci_core_vnic_attachments" "this" {
  availability_domain = var.availability_domain
  compartment_id      = var.compartment_id
  instance_id         = var.instance_id
  vnic_id             = var.vnic_id

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
output "id" {
  description = "returns a string"
  value       = data.oci_core_vnic_attachments.this.id
}

output "vnic_attachments" {
  description = "returns a list of object"
  value       = data.oci_core_vnic_attachments.this.vnic_attachments
}

output "this" {
  value = oci_core_vnic_attachments.this
}
```

[top](#index)