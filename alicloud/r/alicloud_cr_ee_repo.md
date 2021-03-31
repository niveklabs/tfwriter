# alicloud_cr_ee_repo

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cr_ee_repo" {
  source = "./modules/alicloud/r/alicloud_cr_ee_repo"

  # detail - (optional) is a type of string
  detail = null
  # instance_id - (required) is a type of string
  instance_id = null
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

variable "instance_id" {
  description = "(required)"
  type        = string
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
resource "alicloud_cr_ee_repo" "this" {
  detail      = var.detail
  instance_id = var.instance_id
  name        = var.name
  namespace   = var.namespace
  repo_type   = var.repo_type
  summary     = var.summary
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cr_ee_repo.this.id
}

output "repo_id" {
  description = "returns a string"
  value       = alicloud_cr_ee_repo.this.repo_id
}

output "this" {
  value = alicloud_cr_ee_repo.this
}
```

[top](#index)