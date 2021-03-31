# oci_waas_http_redirect

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
module "oci_waas_http_redirect" {
  source = "./modules/oci/r/oci_waas_http_redirect"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # domain - (required) is a type of string
  domain = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # response_code - (optional) is a type of number
  response_code = null

  target = [{
    host     = null
    path     = null
    port     = null
    protocol = null
    query    = null
  }]

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

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "response_code" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "target" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      host     = string
      path     = string
      port     = number
      protocol = string
      query    = string
    }
  ))
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
resource "oci_waas_http_redirect" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  display_name   = var.display_name
  domain         = var.domain
  freeform_tags  = var.freeform_tags
  response_code  = var.response_code

  dynamic "target" {
    for_each = var.target
    content {
      host     = target.value["host"]
      path     = target.value["path"]
      port     = target.value["port"]
      protocol = target.value["protocol"]
      query    = target.value["query"]
    }
  }

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
  value       = oci_waas_http_redirect.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_waas_http_redirect.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_waas_http_redirect.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_waas_http_redirect.this.id
}

output "response_code" {
  description = "returns a number"
  value       = oci_waas_http_redirect.this.response_code
}

output "state" {
  description = "returns a string"
  value       = oci_waas_http_redirect.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_waas_http_redirect.this.time_created
}

output "this" {
  value = oci_waas_http_redirect.this
}
```

[top](#index)