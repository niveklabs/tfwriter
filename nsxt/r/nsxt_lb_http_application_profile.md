# nsxt_lb_http_application_profile

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_lb_http_application_profile" {
  source = "./modules/nsxt/r/nsxt_lb_http_application_profile"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # http_redirect_to - (optional) is a type of string
  http_redirect_to = null
  # http_redirect_to_https - (optional) is a type of bool
  http_redirect_to_https = null
  # idle_timeout - (optional) is a type of number
  idle_timeout = null
  # ntlm - (optional) is a type of bool
  ntlm = null
  # request_body_size - (optional) is a type of number
  request_body_size = null
  # request_header_size - (optional) is a type of number
  request_header_size = null
  # response_timeout - (optional) is a type of number
  response_timeout = null
  # x_forwarded_for - (optional) is a type of string
  x_forwarded_for = null

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
  type        = string
  default     = null
}

variable "http_redirect_to" {
  description = "(optional) - A URL that incoming requests for that virtual server can be temporarily redirected to, If a website is temporarily down or has moved"
  type        = string
  default     = null
}

variable "http_redirect_to_https" {
  description = "(optional) - A boolean flag which reflects whether the client will automatically be redirected to use SSL"
  type        = bool
  default     = null
}

variable "idle_timeout" {
  description = "(optional) - Timeout in seconds to specify how long an HTTP application can remain idle"
  type        = number
  default     = null
}

variable "ntlm" {
  description = "(optional) - A boolean flag which reflects whether NTLM challenge/response methodology will be used over HTTP"
  type        = bool
  default     = null
}

variable "request_body_size" {
  description = "(optional) - Maximum request body size in bytes (Unlimited if not specified)"
  type        = number
  default     = null
}

variable "request_header_size" {
  description = "(optional) - Maximum request header size in bytes. Requests with larger header size will be processed as best effort whereas a request with header below this specified size is guaranteed to be processed"
  type        = number
  default     = null
}

variable "response_timeout" {
  description = "(optional) - Number of seconds waiting for the server response before the connection is closed"
  type        = number
  default     = null
}

variable "x_forwarded_for" {
  description = "(optional) - When this value is set, the x_forwarded_for header in the incoming request will be inserted or replaced"
  type        = string
  default     = null
}

variable "tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      scope = string
      tag   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_lb_http_application_profile" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # http_redirect_to - (optional) is a type of string
  http_redirect_to = var.http_redirect_to
  # http_redirect_to_https - (optional) is a type of bool
  http_redirect_to_https = var.http_redirect_to_https
  # idle_timeout - (optional) is a type of number
  idle_timeout = var.idle_timeout
  # ntlm - (optional) is a type of bool
  ntlm = var.ntlm
  # request_body_size - (optional) is a type of number
  request_body_size = var.request_body_size
  # request_header_size - (optional) is a type of number
  request_header_size = var.request_header_size
  # response_timeout - (optional) is a type of number
  response_timeout = var.response_timeout
  # x_forwarded_for - (optional) is a type of string
  x_forwarded_for = var.x_forwarded_for

  dynamic "tag" {
    for_each = var.tag
    content {
      # scope - (optional) is a type of string
      scope = tag.value["scope"]
      # tag - (optional) is a type of string
      tag = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = nsxt_lb_http_application_profile.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_lb_http_application_profile.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_lb_http_application_profile.this.revision
}

output "this" {
  value = nsxt_lb_http_application_profile.this
}
```

[top](#index)