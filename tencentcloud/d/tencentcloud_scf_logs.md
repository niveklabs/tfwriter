# tencentcloud_scf_logs

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "tencentcloud_scf_logs" {
  source = "./modules/tencentcloud/d/tencentcloud_scf_logs"

  # end_time - (optional) is a type of string
  end_time = null
  # function_name - (required) is a type of string
  function_name = null
  # invoke_request_id - (optional) is a type of string
  invoke_request_id = null
  # limit - (optional) is a type of number
  limit = null
  # namespace - (optional) is a type of string
  namespace = null
  # offset - (optional) is a type of number
  offset = null
  # order - (optional) is a type of string
  order = null
  # order_by - (optional) is a type of string
  order_by = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # ret_code - (optional) is a type of string
  ret_code = null
  # start_time - (optional) is a type of string
  start_time = null
}
```

[top](#index)

### Variables

```terraform
variable "end_time" {
  description = "(optional) - The end time of the query, the format is `2017-05-16 20:00:00`, which can only be within one day from `start_time`."
  type        = string
  default     = null
}

variable "function_name" {
  description = "(required) - Name of the SCF function to be queried."
  type        = string
}

variable "invoke_request_id" {
  description = "(optional) - Corresponding requestId when executing function."
  type        = string
  default     = null
}

variable "limit" {
  description = "(optional) - Number of logs, the default is `10000`, offset+limit cannot be greater than 10000."
  type        = number
  default     = null
}

variable "namespace" {
  description = "(optional) - Namespace of the SCF function to be queried."
  type        = string
  default     = null
}

variable "offset" {
  description = "(optional) - Log offset, default is `0`, offset+limit cannot be greater than 10000."
  type        = number
  default     = null
}

variable "order" {
  description = "(optional) - Order to sort the log, optional values `desc` and `asc`, default `desc`."
  type        = string
  default     = null
}

variable "order_by" {
  description = "(optional) - Sort the logs according to the following fields: `function_name`, `duration`, `mem_usage`, `start_time`, default `start_time`."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "ret_code" {
  description = "(optional) - Use to filter log, optional value: `not0` only returns the error log. `is0` only returns the correct log. `TimeLimitExceeded` returns the log of the function call timeout. `ResourceLimitExceeded` returns the function call generation resource overrun log. `UserCodeException` returns logs of the user code error that occurred in the function call. Not passing the parameter means returning all logs."
  type        = string
  default     = null
}

variable "start_time" {
  description = "(optional) - The start time of the query, the format is `2017-05-16 20:00:00`, which can only be within one day from `end_time`."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_scf_logs" "this" {
  # end_time - (optional) is a type of string
  end_time = var.end_time
  # function_name - (required) is a type of string
  function_name = var.function_name
  # invoke_request_id - (optional) is a type of string
  invoke_request_id = var.invoke_request_id
  # limit - (optional) is a type of number
  limit = var.limit
  # namespace - (optional) is a type of string
  namespace = var.namespace
  # offset - (optional) is a type of number
  offset = var.offset
  # order - (optional) is a type of string
  order = var.order
  # order_by - (optional) is a type of string
  order_by = var.order_by
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # ret_code - (optional) is a type of string
  ret_code = var.ret_code
  # start_time - (optional) is a type of string
  start_time = var.start_time
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_scf_logs.this.id
}

output "logs" {
  description = "returns a list of object"
  value       = data.tencentcloud_scf_logs.this.logs
}

output "this" {
  value = tencentcloud_scf_logs.this
}
```

[top](#index)