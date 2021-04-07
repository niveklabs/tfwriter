# tencentcloud_scf_function

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_scf_function" {
  source = "./modules/tencentcloud/r/tencentcloud_scf_function"

  # cls_logset_id - (optional) is a type of string
  cls_logset_id = null
  # cls_topic_id - (optional) is a type of string
  cls_topic_id = null
  # cos_bucket_name - (optional) is a type of string
  cos_bucket_name = null
  # cos_bucket_region - (optional) is a type of string
  cos_bucket_region = null
  # cos_object_name - (optional) is a type of string
  cos_object_name = null
  # description - (optional) is a type of string
  description = null
  # environment - (optional) is a type of map of string
  environment = {}
  # handler - (required) is a type of string
  handler = null
  # l5_enable - (optional) is a type of bool
  l5_enable = null
  # mem_size - (optional) is a type of number
  mem_size = null
  # name - (required) is a type of string
  name = null
  # namespace - (optional) is a type of string
  namespace = null
  # role - (optional) is a type of string
  role = null
  # runtime - (required) is a type of string
  runtime = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # timeout - (optional) is a type of number
  timeout = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
  # zip_file - (optional) is a type of string
  zip_file = null

  triggers = [{
    cos_region   = null
    name         = null
    trigger_desc = null
    type         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cls_logset_id" {
  description = "(optional) - cls logset id of the SCF function."
  type        = string
  default     = null
}

variable "cls_topic_id" {
  description = "(optional) - cls topic id of the SCF function."
  type        = string
  default     = null
}

variable "cos_bucket_name" {
  description = "(optional) - Cos bucket name of the SCF function, such as `cos-1234567890`, conflict with `zip_file`."
  type        = string
  default     = null
}

variable "cos_bucket_region" {
  description = "(optional) - Cos bucket region of the SCF function, conflict with `zip_file`."
  type        = string
  default     = null
}

variable "cos_object_name" {
  description = "(optional) - Cos object name of the SCF function, should have suffix `.zip` or `.jar`, conflict with `zip_file`."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Description of the SCF function. Description supports English letters, numbers, spaces, commas, newlines, periods and Chinese, the maximum length is 1000."
  type        = string
  default     = null
}

variable "environment" {
  description = "(optional) - Environment of the SCF function."
  type        = map(string)
  default     = null
}

variable "handler" {
  description = "(required) - Handler of the SCF function. The format of name is `<filename>.<method_name>`, and it supports 26 English letters, numbers, connectors, and underscores, it should start with a letter. The last character cannot be `-` or `_`. Available length is 2-60."
  type        = string
}

variable "l5_enable" {
  description = "(optional) - Enable L5 for SCF function, default is `false`."
  type        = bool
  default     = null
}

variable "mem_size" {
  description = "(optional) - Memory size of the SCF function, unit is MB. The default is `128`MB. The range is 128M-1536M, and the ladder is 128M."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the SCF function. Name supports 26 English letters, numbers, connectors, and underscores, it should start with a letter. The last character cannot be `-` or `_`. Available length is 2-60."
  type        = string
}

variable "namespace" {
  description = "(optional) - Namespace of the SCF function, default is `default`."
  type        = string
  default     = null
}

variable "role" {
  description = "(optional) - Role of the SCF function."
  type        = string
  default     = null
}

variable "runtime" {
  description = "(required) - Runtime of the SCF function, only supports `Python2.7`, `Python3.6`, `Nodejs6.10`, `Nodejs8.9`, `Nodejs10.15`, `PHP5`, `PHP7`, `Golang1`, and `Java8`."
  type        = string
}

variable "subnet_id" {
  description = "(optional) - Subnet ID of the SCF function."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags of the SCF function."
  type        = map(string)
  default     = null
}

variable "timeout" {
  description = "(optional) - Timeout of the SCF function, unit is second. Default `3`. Available value is 1-900."
  type        = number
  default     = null
}

variable "vpc_id" {
  description = "(optional) - VPC ID of the SCF function."
  type        = string
  default     = null
}

variable "zip_file" {
  description = "(optional) - Zip file of the SCF function, conflict with `cos_bucket_name`, `cos_object_name`, `cos_bucket_region`."
  type        = string
  default     = null
}

variable "triggers" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cos_region   = string
      name         = string
      trigger_desc = string
      type         = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_scf_function" "this" {
  # cls_logset_id - (optional) is a type of string
  cls_logset_id = var.cls_logset_id
  # cls_topic_id - (optional) is a type of string
  cls_topic_id = var.cls_topic_id
  # cos_bucket_name - (optional) is a type of string
  cos_bucket_name = var.cos_bucket_name
  # cos_bucket_region - (optional) is a type of string
  cos_bucket_region = var.cos_bucket_region
  # cos_object_name - (optional) is a type of string
  cos_object_name = var.cos_object_name
  # description - (optional) is a type of string
  description = var.description
  # environment - (optional) is a type of map of string
  environment = var.environment
  # handler - (required) is a type of string
  handler = var.handler
  # l5_enable - (optional) is a type of bool
  l5_enable = var.l5_enable
  # mem_size - (optional) is a type of number
  mem_size = var.mem_size
  # name - (required) is a type of string
  name = var.name
  # namespace - (optional) is a type of string
  namespace = var.namespace
  # role - (optional) is a type of string
  role = var.role
  # runtime - (required) is a type of string
  runtime = var.runtime
  # subnet_id - (optional) is a type of string
  subnet_id = var.subnet_id
  # tags - (optional) is a type of map of string
  tags = var.tags
  # timeout - (optional) is a type of number
  timeout = var.timeout
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id
  # zip_file - (optional) is a type of string
  zip_file = var.zip_file

  dynamic "triggers" {
    for_each = var.triggers
    content {
      # cos_region - (optional) is a type of string
      cos_region = triggers.value["cos_region"]
      # name - (required) is a type of string
      name = triggers.value["name"]
      # trigger_desc - (required) is a type of string
      trigger_desc = triggers.value["trigger_desc"]
      # type - (required) is a type of string
      type = triggers.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "code_error" {
  description = "returns a string"
  value       = tencentcloud_scf_function.this.code_error
}

output "code_result" {
  description = "returns a string"
  value       = tencentcloud_scf_function.this.code_result
}

output "code_size" {
  description = "returns a number"
  value       = tencentcloud_scf_function.this.code_size
}

output "eip_fixed" {
  description = "returns a bool"
  value       = tencentcloud_scf_function.this.eip_fixed
}

output "eips" {
  description = "returns a list of string"
  value       = tencentcloud_scf_function.this.eips
}

output "err_no" {
  description = "returns a number"
  value       = tencentcloud_scf_function.this.err_no
}

output "host" {
  description = "returns a string"
  value       = tencentcloud_scf_function.this.host
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_scf_function.this.id
}

output "install_dependency" {
  description = "returns a bool"
  value       = tencentcloud_scf_function.this.install_dependency
}

output "modify_time" {
  description = "returns a string"
  value       = tencentcloud_scf_function.this.modify_time
}

output "status" {
  description = "returns a string"
  value       = tencentcloud_scf_function.this.status
}

output "status_desc" {
  description = "returns a string"
  value       = tencentcloud_scf_function.this.status_desc
}

output "trigger_info" {
  description = "returns a list of object"
  value       = tencentcloud_scf_function.this.trigger_info
}

output "vip" {
  description = "returns a string"
  value       = tencentcloud_scf_function.this.vip
}

output "this" {
  value = tencentcloud_scf_function.this
}
```

[top](#index)