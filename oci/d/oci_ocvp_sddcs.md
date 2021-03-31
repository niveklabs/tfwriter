# oci_ocvp_sddcs

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
module "oci_ocvp_sddcs" {
  source = "./modules/oci/d/oci_ocvp_sddcs"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # compute_availability_domain - (optional) is a type of string
  compute_availability_domain = null
  # display_name - (optional) is a type of string
  display_name = null
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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "compute_availability_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
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
data "oci_ocvp_sddcs" "this" {
  compartment_id              = var.compartment_id
  compute_availability_domain = var.compute_availability_domain
  display_name                = var.display_name
  state                       = var.state

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
  value       = data.oci_ocvp_sddcs.this.id
}

output "sddc_collection" {
  description = "returns a list of object"
  value       = data.oci_ocvp_sddcs.this.sddc_collection
}

output "this" {
  value = oci_ocvp_sddcs.this
}
```

[top](#index)