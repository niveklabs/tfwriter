# oci_mysql_channel

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_mysql_channel" {
  source = [{
    hostname    = null
    password    = null
    port        = null
    source_type = null
    ssl_ca_certificate = [{
      certificate_type = null
      contents         = null
    }]
    ssl_mode = null
    username = null
  }]

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_enabled - (optional) is a type of bool
  is_enabled = null


  target = [{
    applier_username = null
    channel_name     = null
    db_system_id     = null
    target_type      = null
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
  description = "(optional)"
  type        = string
  default     = null
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

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "is_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "source" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      hostname    = string
      password    = string
      port        = number
      source_type = string
      ssl_ca_certificate = list(object(
        {
          certificate_type = string
          contents         = string
        }
      ))
      ssl_mode = string
      username = string
    }
  ))
}

variable "target" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      applier_username = string
      channel_name     = string
      db_system_id     = string
      target_type      = string
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
resource "oci_mysql_channel" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  description    = var.description
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags
  is_enabled     = var.is_enabled

  dynamic "source" {
    for_each = var.source
    content {
      hostname    = source.value["hostname"]
      password    = source.value["password"]
      port        = source.value["port"]
      source_type = source.value["source_type"]
      ssl_mode    = source.value["ssl_mode"]
      username    = source.value["username"]

      dynamic "ssl_ca_certificate" {
        for_each = source.value.ssl_ca_certificate
        content {
          certificate_type = ssl_ca_certificate.value["certificate_type"]
          contents         = ssl_ca_certificate.value["contents"]
        }
      }

    }
  }

  dynamic "target" {
    for_each = var.target
    content {
      applier_username = target.value["applier_username"]
      channel_name     = target.value["channel_name"]
      db_system_id     = target.value["db_system_id"]
      target_type      = target.value["target_type"]
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
output "compartment_id" {
  description = "returns a string"
  value       = oci_mysql_channel.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_mysql_channel.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_mysql_channel.this.description
}

output "display_name" {
  description = "returns a string"
  value       = oci_mysql_channel.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_mysql_channel.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_mysql_channel.this.id
}

output "is_enabled" {
  description = "returns a bool"
  value       = oci_mysql_channel.this.is_enabled
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_mysql_channel.this.lifecycle_details
}

output "state" {
  description = "returns a string"
  value       = oci_mysql_channel.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_mysql_channel.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_mysql_channel.this.time_updated
}

output "this" {
  value = oci_mysql_channel.this
}
```

[top](#index)