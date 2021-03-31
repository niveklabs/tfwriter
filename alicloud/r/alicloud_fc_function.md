# alicloud_fc_function

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_fc_function" {
  source = "./modules/alicloud/r/alicloud_fc_function"

  # ca_port - (optional) is a type of number
  ca_port = null
  # code_checksum - (optional) is a type of string
  code_checksum = null
  # description - (optional) is a type of string
  description = null
  # environment_variables - (optional) is a type of map of string
  environment_variables = {}
  # filename - (optional) is a type of string
  filename = null
  # handler - (required) is a type of string
  handler = null
  # initialization_timeout - (optional) is a type of number
  initialization_timeout = null
  # initializer - (optional) is a type of string
  initializer = null
  # instance_concurrency - (optional) is a type of number
  instance_concurrency = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # memory_size - (optional) is a type of number
  memory_size = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # oss_bucket - (optional) is a type of string
  oss_bucket = null
  # oss_key - (optional) is a type of string
  oss_key = null
  # runtime - (required) is a type of string
  runtime = null
  # service - (required) is a type of string
  service = null
  # timeout - (optional) is a type of number
  timeout = null

  custom_container_config = [{
    args    = null
    command = null
    image   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "ca_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "code_checksum" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "environment_variables" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "filename" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "handler" {
  description = "(required)"
  type        = string
}

variable "initialization_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "initializer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_concurrency" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "instance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "memory_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "oss_bucket" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "oss_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "runtime" {
  description = "(required)"
  type        = string
}

variable "service" {
  description = "(required)"
  type        = string
}

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "custom_container_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      args    = string
      command = string
      image   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_fc_function" "this" {
  ca_port                = var.ca_port
  code_checksum          = var.code_checksum
  description            = var.description
  environment_variables  = var.environment_variables
  filename               = var.filename
  handler                = var.handler
  initialization_timeout = var.initialization_timeout
  initializer            = var.initializer
  instance_concurrency   = var.instance_concurrency
  instance_type          = var.instance_type
  memory_size            = var.memory_size
  name                   = var.name
  name_prefix            = var.name_prefix
  oss_bucket             = var.oss_bucket
  oss_key                = var.oss_key
  runtime                = var.runtime
  service                = var.service
  timeout                = var.timeout

  dynamic "custom_container_config" {
    for_each = var.custom_container_config
    content {
      args    = custom_container_config.value["args"]
      command = custom_container_config.value["command"]
      image   = custom_container_config.value["image"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "code_checksum" {
  description = "returns a string"
  value       = alicloud_fc_function.this.code_checksum
}

output "function_id" {
  description = "returns a string"
  value       = alicloud_fc_function.this.function_id
}

output "id" {
  description = "returns a string"
  value       = alicloud_fc_function.this.id
}

output "last_modified" {
  description = "returns a string"
  value       = alicloud_fc_function.this.last_modified
}

output "name" {
  description = "returns a string"
  value       = alicloud_fc_function.this.name
}

output "this" {
  value = alicloud_fc_function.this
}
```

[top](#index)