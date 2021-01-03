# fortios_vpnsslweb_realm

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
module "fortios_vpnsslweb_realm" {
  source = "./modules/fortios/r/fortios_vpnsslweb_realm"

  # login_page - (optional) is a type of string
  login_page = null
  # max_concurrent_user - (optional) is a type of number
  max_concurrent_user = null
  # url_path - (optional) is a type of string
  url_path = null
  # virtual_host - (optional) is a type of string
  virtual_host = null
}
```

[top](#index)

### Variables

```terraform
variable "login_page" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_concurrent_user" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "url_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "virtual_host" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_vpnsslweb_realm" "this" {
  login_page          = var.login_page
  max_concurrent_user = var.max_concurrent_user
  url_path            = var.url_path
  virtual_host        = var.virtual_host
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_vpnsslweb_realm.this.id
}

output "max_concurrent_user" {
  description = "returns a number"
  value       = fortios_vpnsslweb_realm.this.max_concurrent_user
}

output "url_path" {
  description = "returns a string"
  value       = fortios_vpnsslweb_realm.this.url_path
}

output "this" {
  value = fortios_vpnsslweb_realm.this
}
```

[top](#index)