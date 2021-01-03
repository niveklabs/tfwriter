# oci_apigateway_certificate

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
module "oci_apigateway_certificate" {
  source = "./modules/oci/r/oci_apigateway_certificate"

  # certificate - (required) is a type of string
  certificate = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # intermediate_certificates - (optional) is a type of string
  intermediate_certificates = null
  # private_key - (required) is a type of string
  private_key = null

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
variable "certificate" {
  description = "(required)"
  type        = string
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

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "intermediate_certificates" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_key" {
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
resource "oci_apigateway_certificate" "this" {
  certificate               = var.certificate
  compartment_id            = var.compartment_id
  defined_tags              = var.defined_tags
  display_name              = var.display_name
  freeform_tags             = var.freeform_tags
  intermediate_certificates = var.intermediate_certificates
  private_key               = var.private_key

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
  value       = oci_apigateway_certificate.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_apigateway_certificate.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_apigateway_certificate.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_apigateway_certificate.this.id
}

output "intermediate_certificates" {
  description = "returns a string"
  value       = oci_apigateway_certificate.this.intermediate_certificates
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_apigateway_certificate.this.lifecycle_details
}

output "state" {
  description = "returns a string"
  value       = oci_apigateway_certificate.this.state
}

output "subject_names" {
  description = "returns a list of string"
  value       = oci_apigateway_certificate.this.subject_names
}

output "time_created" {
  description = "returns a string"
  value       = oci_apigateway_certificate.this.time_created
}

output "time_not_valid_after" {
  description = "returns a string"
  value       = oci_apigateway_certificate.this.time_not_valid_after
}

output "time_updated" {
  description = "returns a string"
  value       = oci_apigateway_certificate.this.time_updated
}

output "this" {
  value = oci_apigateway_certificate.this
}
```

[top](#index)