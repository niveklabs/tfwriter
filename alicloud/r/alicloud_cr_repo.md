# alicloud_cr_repo

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cr_repo" {
  source = "./modules/alicloud/r/alicloud_cr_repo"

  # detail - (optional) is a type of string
  detail = null
  # name - (required) is a type of string
  name = null
  # namespace - (required) is a type of string
  namespace = null
  # repo_type - (required) is a type of string
  repo_type = null
  # summary - (required) is a type of string
  summary = null
}
```

[top](#index)

### Variables

```terraform
variable "detail" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace" {
  description = "(required)"
  type        = string
}

variable "repo_type" {
  description = "(required)"
  type        = string
}

variable "summary" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cr_repo" "this" {
  # detail - (optional) is a type of string
  detail = var.detail
  # name - (required) is a type of string
  name = var.name
  # namespace - (required) is a type of string
  namespace = var.namespace
  # repo_type - (required) is a type of string
  repo_type = var.repo_type
  # summary - (required) is a type of string
  summary = var.summary
}
```

[top](#index)

### Outputs

```terraform
output "domain_list" {
  description = "returns a map of string"
  value       = alicloud_cr_repo.this.domain_list
}

output "id" {
  description = "returns a string"
  value       = alicloud_cr_repo.this.id
}

output "this" {
  value = alicloud_cr_repo.this
}
```

[top](#index)