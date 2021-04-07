# alicloud_dns_resolution_lines

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_dns_resolution_lines" {
  source = "./modules/alicloud/d/alicloud_dns_resolution_lines"

  # domain_name - (optional) is a type of string
  domain_name = null
  # lang - (optional) is a type of string
  lang = null
  # line_codes - (optional) is a type of list of string
  line_codes = []
  # line_display_names - (optional) is a type of list of string
  line_display_names = []
  # line_names - (optional) is a type of list of string
  line_names = []
  # output_file - (optional) is a type of string
  output_file = null
  # user_client_ip - (optional) is a type of string
  user_client_ip = null
}
```

[top](#index)

### Variables

```terraform
variable "domain_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lang" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "line_codes" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "line_display_names" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "line_names" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_client_ip" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_dns_resolution_lines" "this" {
  # domain_name - (optional) is a type of string
  domain_name = var.domain_name
  # lang - (optional) is a type of string
  lang = var.lang
  # line_codes - (optional) is a type of list of string
  line_codes = var.line_codes
  # line_display_names - (optional) is a type of list of string
  line_display_names = var.line_display_names
  # line_names - (optional) is a type of list of string
  line_names = var.line_names
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # user_client_ip - (optional) is a type of string
  user_client_ip = var.user_client_ip
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_dns_resolution_lines.this.id
}

output "line_codes" {
  description = "returns a list of string"
  value       = data.alicloud_dns_resolution_lines.this.line_codes
}

output "line_display_names" {
  description = "returns a list of string"
  value       = data.alicloud_dns_resolution_lines.this.line_display_names
}

output "lines" {
  description = "returns a list of object"
  value       = data.alicloud_dns_resolution_lines.this.lines
}

output "this" {
  value = alicloud_dns_resolution_lines.this
}
```

[top](#index)