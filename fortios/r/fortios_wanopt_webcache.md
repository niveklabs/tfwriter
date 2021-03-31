# fortios_wanopt_webcache

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
module "fortios_wanopt_webcache" {
  source = "./modules/fortios/r/fortios_wanopt_webcache"

  # always_revalidate - (optional) is a type of string
  always_revalidate = null
  # cache_by_default - (optional) is a type of string
  cache_by_default = null
  # cache_cookie - (optional) is a type of string
  cache_cookie = null
  # cache_expired - (optional) is a type of string
  cache_expired = null
  # default_ttl - (optional) is a type of number
  default_ttl = null
  # external - (optional) is a type of string
  external = null
  # fresh_factor - (optional) is a type of number
  fresh_factor = null
  # host_validate - (optional) is a type of string
  host_validate = null
  # ignore_conditional - (optional) is a type of string
  ignore_conditional = null
  # ignore_ie_reload - (optional) is a type of string
  ignore_ie_reload = null
  # ignore_ims - (optional) is a type of string
  ignore_ims = null
  # ignore_pnc - (optional) is a type of string
  ignore_pnc = null
  # max_object_size - (optional) is a type of number
  max_object_size = null
  # max_ttl - (optional) is a type of number
  max_ttl = null
  # min_ttl - (optional) is a type of number
  min_ttl = null
  # neg_resp_time - (optional) is a type of number
  neg_resp_time = null
  # reval_pnc - (optional) is a type of string
  reval_pnc = null
}
```

[top](#index)

### Variables

```terraform
variable "always_revalidate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cache_by_default" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cache_cookie" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cache_expired" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "external" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fresh_factor" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "host_validate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ignore_conditional" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ignore_ie_reload" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ignore_ims" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ignore_pnc" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_object_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "neg_resp_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reval_pnc" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wanopt_webcache" "this" {
  always_revalidate  = var.always_revalidate
  cache_by_default   = var.cache_by_default
  cache_cookie       = var.cache_cookie
  cache_expired      = var.cache_expired
  default_ttl        = var.default_ttl
  external           = var.external
  fresh_factor       = var.fresh_factor
  host_validate      = var.host_validate
  ignore_conditional = var.ignore_conditional
  ignore_ie_reload   = var.ignore_ie_reload
  ignore_ims         = var.ignore_ims
  ignore_pnc         = var.ignore_pnc
  max_object_size    = var.max_object_size
  max_ttl            = var.max_ttl
  min_ttl            = var.min_ttl
  neg_resp_time      = var.neg_resp_time
  reval_pnc          = var.reval_pnc
}
```

[top](#index)

### Outputs

```terraform
output "always_revalidate" {
  description = "returns a string"
  value       = fortios_wanopt_webcache.this.always_revalidate
}

output "cache_by_default" {
  description = "returns a string"
  value       = fortios_wanopt_webcache.this.cache_by_default
}

output "cache_cookie" {
  description = "returns a string"
  value       = fortios_wanopt_webcache.this.cache_cookie
}

output "cache_expired" {
  description = "returns a string"
  value       = fortios_wanopt_webcache.this.cache_expired
}

output "default_ttl" {
  description = "returns a number"
  value       = fortios_wanopt_webcache.this.default_ttl
}

output "external" {
  description = "returns a string"
  value       = fortios_wanopt_webcache.this.external
}

output "fresh_factor" {
  description = "returns a number"
  value       = fortios_wanopt_webcache.this.fresh_factor
}

output "host_validate" {
  description = "returns a string"
  value       = fortios_wanopt_webcache.this.host_validate
}

output "id" {
  description = "returns a string"
  value       = fortios_wanopt_webcache.this.id
}

output "ignore_conditional" {
  description = "returns a string"
  value       = fortios_wanopt_webcache.this.ignore_conditional
}

output "ignore_ie_reload" {
  description = "returns a string"
  value       = fortios_wanopt_webcache.this.ignore_ie_reload
}

output "ignore_ims" {
  description = "returns a string"
  value       = fortios_wanopt_webcache.this.ignore_ims
}

output "ignore_pnc" {
  description = "returns a string"
  value       = fortios_wanopt_webcache.this.ignore_pnc
}

output "max_object_size" {
  description = "returns a number"
  value       = fortios_wanopt_webcache.this.max_object_size
}

output "max_ttl" {
  description = "returns a number"
  value       = fortios_wanopt_webcache.this.max_ttl
}

output "min_ttl" {
  description = "returns a number"
  value       = fortios_wanopt_webcache.this.min_ttl
}

output "neg_resp_time" {
  description = "returns a number"
  value       = fortios_wanopt_webcache.this.neg_resp_time
}

output "reval_pnc" {
  description = "returns a string"
  value       = fortios_wanopt_webcache.this.reval_pnc
}

output "this" {
  value = fortios_wanopt_webcache.this
}
```

[top](#index)