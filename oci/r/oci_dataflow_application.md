# oci_dataflow_application

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
module "oci_dataflow_application" {
  source = "./modules/oci/r/oci_dataflow_application"

  # archive_uri - (optional) is a type of string
  archive_uri = null
  # arguments - (optional) is a type of list of string
  arguments = []
  # class_name - (optional) is a type of string
  class_name = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # configuration - (optional) is a type of map of string
  configuration = {}
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # driver_shape - (required) is a type of string
  driver_shape = null
  # executor_shape - (required) is a type of string
  executor_shape = null
  # file_uri - (required) is a type of string
  file_uri = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # language - (required) is a type of string
  language = null
  # logs_bucket_uri - (optional) is a type of string
  logs_bucket_uri = null
  # num_executors - (required) is a type of number
  num_executors = null
  # private_endpoint_id - (optional) is a type of string
  private_endpoint_id = null
  # spark_version - (required) is a type of string
  spark_version = null
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
variable "archive_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "arguments" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "class_name" {
  description = "(optional)"
  type        = string
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

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "driver_shape" {
  description = "(required)"
  type        = string
}

variable "executor_shape" {
  description = "(required)"
  type        = string
}

variable "file_uri" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "language" {
  description = "(required)"
  type        = string
}

variable "logs_bucket_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "num_executors" {
  description = "(required)"
  type        = number
}

variable "private_endpoint_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spark_version" {
  description = "(required)"
  type        = string
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
resource "oci_dataflow_application" "this" {
  archive_uri          = var.archive_uri
  arguments            = var.arguments
  class_name           = var.class_name
  compartment_id       = var.compartment_id
  configuration        = var.configuration
  defined_tags         = var.defined_tags
  description          = var.description
  display_name         = var.display_name
  driver_shape         = var.driver_shape
  executor_shape       = var.executor_shape
  file_uri             = var.file_uri
  freeform_tags        = var.freeform_tags
  language             = var.language
  logs_bucket_uri      = var.logs_bucket_uri
  num_executors        = var.num_executors
  private_endpoint_id  = var.private_endpoint_id
  spark_version        = var.spark_version
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
output "arguments" {
  description = "returns a list of string"
  value       = oci_dataflow_application.this.arguments
}

output "configuration" {
  description = "returns a map of string"
  value       = oci_dataflow_application.this.configuration
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_dataflow_application.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_dataflow_application.this.description
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_dataflow_application.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_dataflow_application.this.id
}

output "logs_bucket_uri" {
  description = "returns a string"
  value       = oci_dataflow_application.this.logs_bucket_uri
}

output "owner_principal_id" {
  description = "returns a string"
  value       = oci_dataflow_application.this.owner_principal_id
}

output "owner_user_name" {
  description = "returns a string"
  value       = oci_dataflow_application.this.owner_user_name
}

output "private_endpoint_id" {
  description = "returns a string"
  value       = oci_dataflow_application.this.private_endpoint_id
}

output "state" {
  description = "returns a string"
  value       = oci_dataflow_application.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_dataflow_application.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_dataflow_application.this.time_updated
}

output "warehouse_bucket_uri" {
  description = "returns a string"
  value       = oci_dataflow_application.this.warehouse_bucket_uri
}

output "this" {
  value = oci_dataflow_application.this
}
```

[top](#index)