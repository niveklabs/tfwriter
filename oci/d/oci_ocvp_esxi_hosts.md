# oci_ocvp_esxi_hosts

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
module "oci_ocvp_esxi_hosts" {
  source = "./modules/oci/d/oci_ocvp_esxi_hosts"

  # compute_instance_id - (optional) is a type of string
  compute_instance_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # sddc_id - (optional) is a type of string
  sddc_id = null
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
variable "compute_instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sddc_id" {
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
data "oci_ocvp_esxi_hosts" "this" {
  compute_instance_id = var.compute_instance_id
  display_name        = var.display_name
  sddc_id             = var.sddc_id
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
output "esxi_host_collection" {
  description = "returns a list of object"
  value       = data.oci_ocvp_esxi_hosts.this.esxi_host_collection
}

output "id" {
  description = "returns a string"
  value       = data.oci_ocvp_esxi_hosts.this.id
}

output "this" {
  value = oci_ocvp_esxi_hosts.this
}
```

[top](#index)