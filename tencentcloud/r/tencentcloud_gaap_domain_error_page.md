# tencentcloud_gaap_domain_error_page

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
module "tencentcloud_gaap_domain_error_page" {
  source = "./modules/tencentcloud/r/tencentcloud_gaap_domain_error_page"

  # body - (required) is a type of string
  body = null
  # clear_headers - (optional) is a type of set of string
  clear_headers = []
  # domain - (required) is a type of string
  domain = null
  # error_codes - (required) is a type of set of number
  error_codes = []
  # listener_id - (required) is a type of string
  listener_id = null
  # new_error_code - (optional) is a type of number
  new_error_code = null
  # set_headers - (optional) is a type of map of string
  set_headers = {}
}
```

[top](#index)

### Variables

```terraform
variable "body" {
  description = "(required) - New response body."
  type        = string
}

variable "clear_headers" {
  description = "(optional) - Response headers to be removed."
  type        = set(string)
  default     = null
}

variable "domain" {
  description = "(required) - HTTP domain."
  type        = string
}

variable "error_codes" {
  description = "(required) - Original error codes."
  type        = set(number)
}

variable "listener_id" {
  description = "(required) - ID of the layer7 listener."
  type        = string
}

variable "new_error_code" {
  description = "(optional) - New error code."
  type        = number
  default     = null
}

variable "set_headers" {
  description = "(optional) - Response headers to be set."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_gaap_domain_error_page" "this" {
  # body - (required) is a type of string
  body = var.body
  # clear_headers - (optional) is a type of set of string
  clear_headers = var.clear_headers
  # domain - (required) is a type of string
  domain = var.domain
  # error_codes - (required) is a type of set of number
  error_codes = var.error_codes
  # listener_id - (required) is a type of string
  listener_id = var.listener_id
  # new_error_code - (optional) is a type of number
  new_error_code = var.new_error_code
  # set_headers - (optional) is a type of map of string
  set_headers = var.set_headers
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_gaap_domain_error_page.this.id
}

output "this" {
  value = tencentcloud_gaap_domain_error_page.this
}
```

[top](#index)