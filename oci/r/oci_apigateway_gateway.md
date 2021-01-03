# oci_apigateway_gateway

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
module "oci_apigateway_gateway" {
  source = "./modules/oci/r/oci_apigateway_gateway"

  # certificate_id - (optional) is a type of string
  certificate_id = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # endpoint_type - (required) is a type of string
  endpoint_type = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
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
variable "certificate_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

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

variable "endpoint_type" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
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
resource "oci_apigateway_gateway" "this" {
  certificate_id = var.certificate_id
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  display_name   = var.display_name
  endpoint_type  = var.endpoint_type
  freeform_tags  = var.freeform_tags
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
output "certificate_id" {
  description = "returns a string"
  value       = oci_apigateway_gateway.this.certificate_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_apigateway_gateway.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_apigateway_gateway.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_apigateway_gateway.this.freeform_tags
}

output "hostname" {
  description = "returns a string"
  value       = oci_apigateway_gateway.this.hostname
}

output "id" {
  description = "returns a string"
  value       = oci_apigateway_gateway.this.id
}

output "ip_addresses" {
  description = "returns a list of object"
  value       = oci_apigateway_gateway.this.ip_addresses
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_apigateway_gateway.this.lifecycle_details
}

output "state" {
  description = "returns a string"
  value       = oci_apigateway_gateway.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_apigateway_gateway.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_apigateway_gateway.this.time_updated
}

output "this" {
  value = oci_apigateway_gateway.this
}
```

[top](#index)