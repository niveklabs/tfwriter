# checkpoint_management_dns_domain

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_dns_domain" {
  source = "./modules/checkpoint/r/checkpoint_management_dns_domain"

  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # is_sub_domain - (optional) is a type of bool
  is_sub_domain = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "color" {
  description = "(optional) - Color of the object. Should be one of existing colors."
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional) - Comments string."
  type        = string
  default     = null
}

variable "ignore_errors" {
  description = "(optional) - Apply changes ignoring errors. You won't be able to publish such a changes. If ignore-warnings flag was omitted - warnings will also be ignored."
  type        = bool
  default     = null
}

variable "ignore_warnings" {
  description = "(optional) - Apply changes ignoring warnings."
  type        = bool
  default     = null
}

variable "is_sub_domain" {
  description = "(optional) - Whether to match sub-domains in addition to the domain itself."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Object name."
  type        = string
}

variable "tags" {
  description = "(optional) - Collection of tag identifiers."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_dns_domain" "this" {
  # color - (optional) is a type of string
  color = var.color
  # comments - (optional) is a type of string
  comments = var.comments
  # ignore_errors - (optional) is a type of bool
  ignore_errors = var.ignore_errors
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = var.ignore_warnings
  # is_sub_domain - (optional) is a type of bool
  is_sub_domain = var.is_sub_domain
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of set of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_dns_domain.this.id
}

output "this" {
  value = checkpoint_management_dns_domain.this
}
```

[top](#index)