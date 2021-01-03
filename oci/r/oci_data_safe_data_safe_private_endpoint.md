# oci_data_safe_data_safe_private_endpoint

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_data_safe_data_safe_private_endpoint" {
  source = "./modules/oci/r/oci_data_safe_data_safe_private_endpoint"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # nsg_ids - (optional) is a type of set of string
  nsg_ids = []
  # private_endpoint_ip - (optional) is a type of string
  private_endpoint_ip = null
  # subnet_id - (required) is a type of string
  subnet_id = null
  # vcn_id - (required) is a type of string
  vcn_id = null

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
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "nsg_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "private_endpoint_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(required)"
  type        = string
}

variable "vcn_id" {
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
resource "oci_data_safe_data_safe_private_endpoint" "this" {
  compartment_id      = var.compartment_id
  defined_tags        = var.defined_tags
  description         = var.description
  display_name        = var.display_name
  freeform_tags       = var.freeform_tags
  nsg_ids             = var.nsg_ids
  private_endpoint_ip = var.private_endpoint_ip
  subnet_id           = var.subnet_id
  vcn_id              = var.vcn_id

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
  value       = oci_data_safe_data_safe_private_endpoint.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_data_safe_data_safe_private_endpoint.this.description
}

output "endpoint_fqdn" {
  description = "returns a string"
  value       = oci_data_safe_data_safe_private_endpoint.this.endpoint_fqdn
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_data_safe_data_safe_private_endpoint.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_data_safe_data_safe_private_endpoint.this.id
}

output "nsg_ids" {
  description = "returns a set of string"
  value       = oci_data_safe_data_safe_private_endpoint.this.nsg_ids
}

output "private_endpoint_id" {
  description = "returns a string"
  value       = oci_data_safe_data_safe_private_endpoint.this.private_endpoint_id
}

output "private_endpoint_ip" {
  description = "returns a string"
  value       = oci_data_safe_data_safe_private_endpoint.this.private_endpoint_ip
}

output "state" {
  description = "returns a string"
  value       = oci_data_safe_data_safe_private_endpoint.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_data_safe_data_safe_private_endpoint.this.time_created
}

output "this" {
  value = oci_data_safe_data_safe_private_endpoint.this
}
```

[top](#index)