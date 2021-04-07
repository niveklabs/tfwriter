# oci_core_instance_console_connection

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
module "oci_core_instance_console_connection" {
  source = "./modules/oci/r/oci_core_instance_console_connection"

  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # instance_id - (required) is a type of string
  instance_id = null
  # public_key - (required) is a type of string
  public_key = null

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
variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "public_key" {
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
resource "oci_core_instance_console_connection" "this" {
  defined_tags  = var.defined_tags
  freeform_tags = var.freeform_tags
  instance_id   = var.instance_id
  public_key    = var.public_key

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
output "compartment_id" {
  description = "returns a string"
  value       = oci_core_instance_console_connection.this.compartment_id
}

output "connection_string" {
  description = "returns a string"
  value       = oci_core_instance_console_connection.this.connection_string
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_instance_console_connection.this.defined_tags
}

output "fingerprint" {
  description = "returns a string"
  value       = oci_core_instance_console_connection.this.fingerprint
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_instance_console_connection.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_instance_console_connection.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_core_instance_console_connection.this.state
}

output "vnc_connection_string" {
  description = "returns a string"
  value       = oci_core_instance_console_connection.this.vnc_connection_string
}

output "this" {
  value = oci_core_instance_console_connection.this
}
```

[top](#index)