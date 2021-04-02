# oci_streaming_stream_pool

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
module "oci_streaming_stream_pool" {
  source = "./modules/oci/r/oci_streaming_stream_pool"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # name - (required) is a type of string
  name = null

  custom_encryption_key = [{
    key_state  = null
    kms_key_id = null
  }]

  kafka_settings = [{
    auto_create_topics_enable = null
    bootstrap_servers         = null
    log_retention_hours       = null
    num_partitions            = null
  }]

  private_endpoint_settings = [{
    nsg_ids             = []
    private_endpoint_ip = null
    subnet_id           = null
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

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "custom_encryption_key" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      key_state  = string
      kms_key_id = string
    }
  ))
  default = []
}

variable "kafka_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auto_create_topics_enable = bool
      bootstrap_servers         = string
      log_retention_hours       = number
      num_partitions            = number
    }
  ))
  default = []
}

variable "private_endpoint_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      nsg_ids             = set(string)
      private_endpoint_ip = string
      subnet_id           = string
    }
  ))
  default = []
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
resource "oci_streaming_stream_pool" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  freeform_tags  = var.freeform_tags
  name           = var.name

  dynamic "custom_encryption_key" {
    for_each = var.custom_encryption_key
    content {
      kms_key_id = custom_encryption_key.value["kms_key_id"]
    }
  }

  dynamic "kafka_settings" {
    for_each = var.kafka_settings
    content {
      auto_create_topics_enable = kafka_settings.value["auto_create_topics_enable"]
      log_retention_hours       = kafka_settings.value["log_retention_hours"]
      num_partitions            = kafka_settings.value["num_partitions"]
    }
  }

  dynamic "private_endpoint_settings" {
    for_each = var.private_endpoint_settings
    content {
      nsg_ids             = private_endpoint_settings.value["nsg_ids"]
      private_endpoint_ip = private_endpoint_settings.value["private_endpoint_ip"]
      subnet_id           = private_endpoint_settings.value["subnet_id"]
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
  value       = oci_streaming_stream_pool.this.defined_tags
}

output "endpoint_fqdn" {
  description = "returns a string"
  value       = oci_streaming_stream_pool.this.endpoint_fqdn
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_streaming_stream_pool.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_streaming_stream_pool.this.id
}

output "is_private" {
  description = "returns a bool"
  value       = oci_streaming_stream_pool.this.is_private
}

output "lifecycle_state_details" {
  description = "returns a string"
  value       = oci_streaming_stream_pool.this.lifecycle_state_details
}

output "state" {
  description = "returns a string"
  value       = oci_streaming_stream_pool.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_streaming_stream_pool.this.time_created
}

output "this" {
  value = oci_streaming_stream_pool.this
}
```

[top](#index)