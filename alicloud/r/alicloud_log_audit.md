# alicloud_log_audit

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_log_audit" {
  source = "./modules/alicloud/r/alicloud_log_audit"

  # aliuid - (required) is a type of string
  aliuid = null
  # display_name - (required) is a type of string
  display_name = null
  # multi_account - (optional) is a type of set of string
  multi_account = []
  # variable_map - (optional) is a type of map of string
  variable_map = {}
}
```

[top](#index)

### Variables

```terraform
variable "aliuid" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "multi_account" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "variable_map" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_log_audit" "this" {
  aliuid        = var.aliuid
  display_name  = var.display_name
  multi_account = var.multi_account
  variable_map  = var.variable_map
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_log_audit.this.id
}

output "this" {
  value = alicloud_log_audit.this
}
```

[top](#index)