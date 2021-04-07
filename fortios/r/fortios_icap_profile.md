# fortios_icap_profile

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_icap_profile" {
  source = "./modules/fortios/r/fortios_icap_profile"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # methods - (optional) is a type of string
  methods = null
  # name - (optional) is a type of string
  name = null
  # preview - (optional) is a type of string
  preview = null
  # preview_data_length - (optional) is a type of number
  preview_data_length = null
  # replacemsg_group - (optional) is a type of string
  replacemsg_group = null
  # request - (optional) is a type of string
  request = null
  # request_failure - (optional) is a type of string
  request_failure = null
  # request_path - (optional) is a type of string
  request_path = null
  # request_server - (optional) is a type of string
  request_server = null
  # respmod_default_action - (optional) is a type of string
  respmod_default_action = null
  # response - (optional) is a type of string
  response = null
  # response_failure - (optional) is a type of string
  response_failure = null
  # response_path - (optional) is a type of string
  response_path = null
  # response_req_hdr - (optional) is a type of string
  response_req_hdr = null
  # response_server - (optional) is a type of string
  response_server = null
  # streaming_content_bypass - (optional) is a type of string
  streaming_content_bypass = null

  icap_headers = [{
    base64_encoding = null
    content         = null
    id              = null
    name            = null
  }]

  respmod_forward_rules = [{
    action = null
    header_group = [{
      case_sensitivity = null
      header           = null
      header_name      = null
      id               = null
    }]
    host = null
    http_resp_status_code = [{
      code = null
    }]
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "methods" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "preview" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "preview_data_length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "replacemsg_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "request" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "request_failure" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "request_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "request_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "respmod_default_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "response" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "response_failure" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "response_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "response_req_hdr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "response_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "streaming_content_bypass" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "icap_headers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      base64_encoding = string
      content         = string
      id              = number
      name            = string
    }
  ))
  default = []
}

variable "respmod_forward_rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = string
      header_group = list(object(
        {
          case_sensitivity = string
          header           = string
          header_name      = string
          id               = number
        }
      ))
      host = string
      http_resp_status_code = list(object(
        {
          code = number
        }
      ))
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_icap_profile" "this" {
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # methods - (optional) is a type of string
  methods = var.methods
  # name - (optional) is a type of string
  name = var.name
  # preview - (optional) is a type of string
  preview = var.preview
  # preview_data_length - (optional) is a type of number
  preview_data_length = var.preview_data_length
  # replacemsg_group - (optional) is a type of string
  replacemsg_group = var.replacemsg_group
  # request - (optional) is a type of string
  request = var.request
  # request_failure - (optional) is a type of string
  request_failure = var.request_failure
  # request_path - (optional) is a type of string
  request_path = var.request_path
  # request_server - (optional) is a type of string
  request_server = var.request_server
  # respmod_default_action - (optional) is a type of string
  respmod_default_action = var.respmod_default_action
  # response - (optional) is a type of string
  response = var.response
  # response_failure - (optional) is a type of string
  response_failure = var.response_failure
  # response_path - (optional) is a type of string
  response_path = var.response_path
  # response_req_hdr - (optional) is a type of string
  response_req_hdr = var.response_req_hdr
  # response_server - (optional) is a type of string
  response_server = var.response_server
  # streaming_content_bypass - (optional) is a type of string
  streaming_content_bypass = var.streaming_content_bypass

  dynamic "icap_headers" {
    for_each = var.icap_headers
    content {
      # base64_encoding - (optional) is a type of string
      base64_encoding = icap_headers.value["base64_encoding"]
      # content - (optional) is a type of string
      content = icap_headers.value["content"]
      # id - (optional) is a type of number
      id = icap_headers.value["id"]
      # name - (optional) is a type of string
      name = icap_headers.value["name"]
    }
  }

  dynamic "respmod_forward_rules" {
    for_each = var.respmod_forward_rules
    content {
      # action - (optional) is a type of string
      action = respmod_forward_rules.value["action"]
      # host - (optional) is a type of string
      host = respmod_forward_rules.value["host"]
      # name - (optional) is a type of string
      name = respmod_forward_rules.value["name"]

      dynamic "header_group" {
        for_each = respmod_forward_rules.value.header_group
        content {
          # case_sensitivity - (optional) is a type of string
          case_sensitivity = header_group.value["case_sensitivity"]
          # header - (optional) is a type of string
          header = header_group.value["header"]
          # header_name - (optional) is a type of string
          header_name = header_group.value["header_name"]
          # id - (optional) is a type of number
          id = header_group.value["id"]
        }
      }

      dynamic "http_resp_status_code" {
        for_each = respmod_forward_rules.value.http_resp_status_code
        content {
          # code - (optional) is a type of number
          code = http_resp_status_code.value["code"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_icap_profile.this.id
}

output "methods" {
  description = "returns a string"
  value       = fortios_icap_profile.this.methods
}

output "name" {
  description = "returns a string"
  value       = fortios_icap_profile.this.name
}

output "preview" {
  description = "returns a string"
  value       = fortios_icap_profile.this.preview
}

output "preview_data_length" {
  description = "returns a number"
  value       = fortios_icap_profile.this.preview_data_length
}

output "replacemsg_group" {
  description = "returns a string"
  value       = fortios_icap_profile.this.replacemsg_group
}

output "request" {
  description = "returns a string"
  value       = fortios_icap_profile.this.request
}

output "request_failure" {
  description = "returns a string"
  value       = fortios_icap_profile.this.request_failure
}

output "request_path" {
  description = "returns a string"
  value       = fortios_icap_profile.this.request_path
}

output "request_server" {
  description = "returns a string"
  value       = fortios_icap_profile.this.request_server
}

output "respmod_default_action" {
  description = "returns a string"
  value       = fortios_icap_profile.this.respmod_default_action
}

output "response" {
  description = "returns a string"
  value       = fortios_icap_profile.this.response
}

output "response_failure" {
  description = "returns a string"
  value       = fortios_icap_profile.this.response_failure
}

output "response_path" {
  description = "returns a string"
  value       = fortios_icap_profile.this.response_path
}

output "response_req_hdr" {
  description = "returns a string"
  value       = fortios_icap_profile.this.response_req_hdr
}

output "response_server" {
  description = "returns a string"
  value       = fortios_icap_profile.this.response_server
}

output "streaming_content_bypass" {
  description = "returns a string"
  value       = fortios_icap_profile.this.streaming_content_bypass
}

output "this" {
  value = fortios_icap_profile.this
}
```

[top](#index)