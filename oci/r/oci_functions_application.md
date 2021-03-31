# oci_functions_application

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
module "oci_functions_application" {
  source = "./modules/oci/r/oci_functions_application"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # config - (optional) is a type of map of string
  config = {}
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # subnet_ids - (required) is a type of list of string
  subnet_ids = []
  # syslog_url - (optional) is a type of string
  syslog_url = null

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

variable "config" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
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

variable "subnet_ids" {
  description = "(required)"
  type        = list(string)
}

variable "syslog_url" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "oci_functions_application" "this" {
  compartment_id = var.compartment_id
  config         = var.config
  defined_tags   = var.defined_tags
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags
  subnet_ids     = var.subnet_ids
  syslog_url     = var.syslog_url

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
output "config" {
  description = "returns a map of string"
  value       = oci_functions_application.this.config
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_functions_application.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_functions_application.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_functions_application.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_functions_application.this.state
}

output "syslog_url" {
  description = "returns a string"
  value       = oci_functions_application.this.syslog_url
}

output "time_created" {
  description = "returns a string"
  value       = oci_functions_application.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_functions_application.this.time_updated
}

output "this" {
  value = oci_functions_application.this
}
```

[top](#index)