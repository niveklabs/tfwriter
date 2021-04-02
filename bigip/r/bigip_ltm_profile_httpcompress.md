# bigip_ltm_profile_httpcompress

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_profile_httpcompress" {
  source = "./modules/bigip/r/bigip_ltm_profile_httpcompress"

  # content_type_exclude - (optional) is a type of set of string
  content_type_exclude = []
  # content_type_include - (optional) is a type of set of string
  content_type_include = []
  # defaults_from - (optional) is a type of string
  defaults_from = null
  # name - (required) is a type of string
  name = null
  # uri_exclude - (optional) is a type of set of string
  uri_exclude = []
  # uri_include - (optional) is a type of set of string
  uri_include = []
}
```

[top](#index)

### Variables

```terraform
variable "content_type_exclude" {
  description = "(optional) - Specifies a list of content types for compression of HTTP Content-Type responses. Use a string list to specify a list of content types you want to exclude."
  type        = set(string)
  default     = null
}

variable "content_type_include" {
  description = "(optional) - Specifies a list of content types for compression of HTTP Content-Type responses. Use a string list to specify a list of content types you want to compress."
  type        = set(string)
  default     = null
}

variable "defaults_from" {
  description = "(optional) - Use the parent Httpcompress profile"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the Httpcompress Profile"
  type        = string
}

variable "uri_exclude" {
  description = "(optional) - Servers Address"
  type        = set(string)
  default     = null
}

variable "uri_include" {
  description = "(optional) - Servers Address"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_profile_httpcompress" "this" {
  content_type_exclude = var.content_type_exclude
  content_type_include = var.content_type_include
  defaults_from        = var.defaults_from
  name                 = var.name
  uri_exclude          = var.uri_exclude
  uri_include          = var.uri_include
}
```

[top](#index)

### Outputs

```terraform
output "content_type_exclude" {
  description = "returns a set of string"
  value       = bigip_ltm_profile_httpcompress.this.content_type_exclude
}

output "content_type_include" {
  description = "returns a set of string"
  value       = bigip_ltm_profile_httpcompress.this.content_type_include
}

output "defaults_from" {
  description = "returns a string"
  value       = bigip_ltm_profile_httpcompress.this.defaults_from
}

output "id" {
  description = "returns a string"
  value       = bigip_ltm_profile_httpcompress.this.id
}

output "uri_exclude" {
  description = "returns a set of string"
  value       = bigip_ltm_profile_httpcompress.this.uri_exclude
}

output "uri_include" {
  description = "returns a set of string"
  value       = bigip_ltm_profile_httpcompress.this.uri_include
}

output "this" {
  value = bigip_ltm_profile_httpcompress.this
}
```

[top](#index)