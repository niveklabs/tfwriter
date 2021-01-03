# oci_sch_service_connector

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
module "oci_sch_service_connector" {
  source = [{
    kind = null
    log_sources = [{
      compartment_id = null
      log_group_id   = null
      log_id         = null
    }]
  }]

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
  # state - (optional) is a type of string
  state = null


  target = [{
    bucket             = null
    compartment_id     = null
    function_id        = null
    kind               = null
    metric             = null
    metric_namespace   = null
    namespace          = null
    object_name_prefix = null
    stream_id          = null
    topic_id           = null
  }]

  tasks = [{
    condition = null
    kind      = null
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

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      kind = string
      log_sources = list(object(
        {
          compartment_id = string
          log_group_id   = string
          log_id         = string
        }
      ))
    }
  ))
}

variable "target" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      bucket             = string
      compartment_id     = string
      function_id        = string
      kind               = string
      metric             = string
      metric_namespace   = string
      namespace          = string
      object_name_prefix = string
      stream_id          = string
      topic_id           = string
    }
  ))
}

variable "tasks" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      condition = string
      kind      = string
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
resource "oci_sch_service_connector" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  description    = var.description
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags
  state          = var.state

  dynamic "source" {
    for_each = var.source
    content {
      kind = source.value["kind"]

      dynamic "log_sources" {
        for_each = source.value.log_sources
        content {
          compartment_id = log_sources.value["compartment_id"]
          log_group_id   = log_sources.value["log_group_id"]
          log_id         = log_sources.value["log_id"]
        }
      }

    }
  }

  dynamic "target" {
    for_each = var.target
    content {
      bucket             = target.value["bucket"]
      compartment_id     = target.value["compartment_id"]
      function_id        = target.value["function_id"]
      kind               = target.value["kind"]
      metric             = target.value["metric"]
      metric_namespace   = target.value["metric_namespace"]
      namespace          = target.value["namespace"]
      object_name_prefix = target.value["object_name_prefix"]
      stream_id          = target.value["stream_id"]
      topic_id           = target.value["topic_id"]
    }
  }

  dynamic "tasks" {
    for_each = var.tasks
    content {
      condition = tasks.value["condition"]
      kind      = tasks.value["kind"]
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
  value       = oci_sch_service_connector.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_sch_service_connector.this.description
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_sch_service_connector.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_sch_service_connector.this.id
}

output "lifecyle_details" {
  description = "returns a string"
  value       = oci_sch_service_connector.this.lifecyle_details
}

output "state" {
  description = "returns a string"
  value       = oci_sch_service_connector.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = oci_sch_service_connector.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = oci_sch_service_connector.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_sch_service_connector.this.time_updated
}

output "this" {
  value = oci_sch_service_connector.this
}
```

[top](#index)