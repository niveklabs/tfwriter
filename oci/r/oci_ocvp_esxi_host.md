# oci_ocvp_esxi_host

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "oci_ocvp_esxi_host" {
  source = "./modules/oci/r/oci_ocvp_esxi_host"

  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # sddc_id - (required) is a type of string
  sddc_id = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "sddc_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_ocvp_esxi_host" "this" {
  defined_tags  = var.defined_tags
  display_name  = var.display_name
  freeform_tags = var.freeform_tags
  sddc_id       = var.sddc_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = oci_ocvp_esxi_host.this.compartment_id
}

output "compute_instance_id" {
  description = "returns a string"
  value       = oci_ocvp_esxi_host.this.compute_instance_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_ocvp_esxi_host.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_ocvp_esxi_host.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_ocvp_esxi_host.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_ocvp_esxi_host.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_ocvp_esxi_host.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_ocvp_esxi_host.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_ocvp_esxi_host.this.time_updated
}

output "this" {
  value = oci_ocvp_esxi_host.this
}
```

[top](#index)