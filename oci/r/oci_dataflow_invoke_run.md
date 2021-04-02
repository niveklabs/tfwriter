# oci_dataflow_invoke_run

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
module "oci_dataflow_invoke_run" {
  source = "./modules/oci/r/oci_dataflow_invoke_run"

  # application_id - (required) is a type of string
  application_id = null
  # arguments - (optional) is a type of list of string
  arguments = []
  # asynchronous - (optional) is a type of bool
  asynchronous = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # configuration - (optional) is a type of map of string
  configuration = {}
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # driver_shape - (optional) is a type of string
  driver_shape = null
  # executor_shape - (optional) is a type of string
  executor_shape = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # logs_bucket_uri - (optional) is a type of string
  logs_bucket_uri = null
  # num_executors - (optional) is a type of number
  num_executors = null
  # warehouse_bucket_uri - (optional) is a type of string
  warehouse_bucket_uri = null

  parameters = [{
    name  = null
    value = null
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
variable "application_id" {
  description = "(required)"
  type        = string
}

variable "arguments" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "asynchronous" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "configuration" {
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

variable "driver_shape" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "executor_shape" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "logs_bucket_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "num_executors" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "warehouse_bucket_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parameters" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
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
resource "oci_dataflow_invoke_run" "this" {
  application_id       = var.application_id
  arguments            = var.arguments
  asynchronous         = var.asynchronous
  compartment_id       = var.compartment_id
  configuration        = var.configuration
  defined_tags         = var.defined_tags
  display_name         = var.display_name
  driver_shape         = var.driver_shape
  executor_shape       = var.executor_shape
  freeform_tags        = var.freeform_tags
  logs_bucket_uri      = var.logs_bucket_uri
  num_executors        = var.num_executors
  warehouse_bucket_uri = var.warehouse_bucket_uri

  dynamic "parameters" {
    for_each = var.parameters
    content {
      name  = parameters.value["name"]
      value = parameters.value["value"]
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
output "archive_uri" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.archive_uri
}

output "arguments" {
  description = "returns a list of string"
  value       = oci_dataflow_invoke_run.this.arguments
}

output "class_name" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.class_name
}

output "configuration" {
  description = "returns a map of string"
  value       = oci_dataflow_invoke_run.this.configuration
}

output "data_read_in_bytes" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.data_read_in_bytes
}

output "data_written_in_bytes" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.data_written_in_bytes
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_dataflow_invoke_run.this.defined_tags
}

output "driver_shape" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.driver_shape
}

output "executor_shape" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.executor_shape
}

output "file_uri" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.file_uri
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_dataflow_invoke_run.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.id
}

output "language" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.language
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.lifecycle_details
}

output "logs_bucket_uri" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.logs_bucket_uri
}

output "num_executors" {
  description = "returns a number"
  value       = oci_dataflow_invoke_run.this.num_executors
}

output "opc_request_id" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.opc_request_id
}

output "owner_principal_id" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.owner_principal_id
}

output "owner_user_name" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.owner_user_name
}

output "private_endpoint_dns_zones" {
  description = "returns a list of string"
  value       = oci_dataflow_invoke_run.this.private_endpoint_dns_zones
}

output "private_endpoint_id" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.private_endpoint_id
}

output "private_endpoint_max_host_count" {
  description = "returns a number"
  value       = oci_dataflow_invoke_run.this.private_endpoint_max_host_count
}

output "private_endpoint_nsg_ids" {
  description = "returns a list of string"
  value       = oci_dataflow_invoke_run.this.private_endpoint_nsg_ids
}

output "private_endpoint_subnet_id" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.private_endpoint_subnet_id
}

output "run_duration_in_milliseconds" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.run_duration_in_milliseconds
}

output "spark_version" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.spark_version
}

output "state" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.time_updated
}

output "total_ocpu" {
  description = "returns a number"
  value       = oci_dataflow_invoke_run.this.total_ocpu
}

output "warehouse_bucket_uri" {
  description = "returns a string"
  value       = oci_dataflow_invoke_run.this.warehouse_bucket_uri
}

output "this" {
  value = oci_dataflow_invoke_run.this
}
```

[top](#index)