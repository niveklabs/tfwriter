# oci_ocvp_esxi_host

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
module "oci_ocvp_esxi_host" {
  source = "./modules/oci/d/oci_ocvp_esxi_host"

  # esxi_host_id - (required) is a type of string
  esxi_host_id = null
}
```

[top](#index)

### Variables

```terraform
variable "esxi_host_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_ocvp_esxi_host" "this" {
  esxi_host_id = var.esxi_host_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_ocvp_esxi_host.this.compartment_id
}

output "compute_instance_id" {
  description = "returns a string"
  value       = data.oci_ocvp_esxi_host.this.compute_instance_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_ocvp_esxi_host.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_ocvp_esxi_host.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_ocvp_esxi_host.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_ocvp_esxi_host.this.id
}

output "sddc_id" {
  description = "returns a string"
  value       = data.oci_ocvp_esxi_host.this.sddc_id
}

output "state" {
  description = "returns a string"
  value       = data.oci_ocvp_esxi_host.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_ocvp_esxi_host.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_ocvp_esxi_host.this.time_updated
}

output "this" {
  value = oci_ocvp_esxi_host.this
}
```

[top](#index)