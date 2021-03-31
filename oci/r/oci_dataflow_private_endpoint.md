# oci_dataflow_private_endpoint

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_dataflow_private_endpoint" {
  source = "./modules/oci/r/oci_dataflow_private_endpoint"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # dns_zones - (required) is a type of list of string
  dns_zones = []
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # max_host_count - (optional) is a type of number
  max_host_count = null
  # nsg_ids - (optional) is a type of set of string
  nsg_ids = []
  # subnet_id - (required) is a type of string
  subnet_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
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

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_zones" {
  description = "(required)"
  type        = list(string)
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "max_host_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "nsg_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "subnet_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_dataflow_private_endpoint" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  description    = var.description
  display_name   = var.display_name
  dns_zones      = var.dns_zones
  freeform_tags  = var.freeform_tags
  max_host_count = var.max_host_count
  nsg_ids        = var.nsg_ids
  subnet_id      = var.subnet_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_dataflow_private_endpoint.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_dataflow_private_endpoint.this.description
}

output "display_name" {
  description = "returns a string"
  value       = oci_dataflow_private_endpoint.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_dataflow_private_endpoint.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_dataflow_private_endpoint.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_dataflow_private_endpoint.this.lifecycle_details
}

output "max_host_count" {
  description = "returns a number"
  value       = oci_dataflow_private_endpoint.this.max_host_count
}

output "nsg_ids" {
  description = "returns a set of string"
  value       = oci_dataflow_private_endpoint.this.nsg_ids
}

output "owner_principal_id" {
  description = "returns a string"
  value       = oci_dataflow_private_endpoint.this.owner_principal_id
}

output "owner_user_name" {
  description = "returns a string"
  value       = oci_dataflow_private_endpoint.this.owner_user_name
}

output "state" {
  description = "returns a string"
  value       = oci_dataflow_private_endpoint.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_dataflow_private_endpoint.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_dataflow_private_endpoint.this.time_updated
}

output "this" {
  value = oci_dataflow_private_endpoint.this
}
```

[top](#index)