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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_icap_profile" {
  source = "./modules/fortios/r/fortios_icap_profile"

  # methods - (optional) is a type of string
  methods = null
  # name - (optional) is a type of string
  name = null
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
}
```

[top](#index)

### Variables

```terraform
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
```

[top](#index)

### Resource

```terraform
resource "fortios_icap_profile" "this" {
  methods                  = var.methods
  name                     = var.name
  replacemsg_group         = var.replacemsg_group
  request                  = var.request
  request_failure          = var.request_failure
  request_path             = var.request_path
  request_server           = var.request_server
  response                 = var.response
  response_failure         = var.response_failure
  response_path            = var.response_path
  response_req_hdr         = var.response_req_hdr
  response_server          = var.response_server
  streaming_content_bypass = var.streaming_content_bypass

  dynamic "icap_headers" {
    for_each = var.icap_headers
    content {
      base64_encoding = icap_headers.value["base64_encoding"]
      content         = icap_headers.value["content"]
      id              = icap_headers.value["id"]
      name            = icap_headers.value["name"]
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