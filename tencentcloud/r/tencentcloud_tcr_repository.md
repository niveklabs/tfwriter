# tencentcloud_tcr_repository

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
module "tencentcloud_tcr_repository" {
  source = "./modules/tencentcloud/r/tencentcloud_tcr_repository"

  # brief_desc - (required) is a type of string
  brief_desc = null
  # description - (required) is a type of string
  description = null
  # instance_id - (required) is a type of string
  instance_id = null
  # name - (required) is a type of string
  name = null
  # namespace_name - (required) is a type of string
  namespace_name = null
}
```

[top](#index)

### Variables

```terraform
variable "brief_desc" {
  description = "(required) - Brief description of the repository. Valid length is [1~100]."
  type        = string
}

variable "description" {
  description = "(required) - Description of the repository. Valid length is [1~1000]."
  type        = string
}

variable "instance_id" {
  description = "(required) - ID of the TCR instance."
  type        = string
}

variable "name" {
  description = "(required) - Name of the TCR repository. Valid length is [2~200]. It can only contain lowercase letters, numbers and separators (`.`, `_`, `-`, `/`), and cannot start, end or continue with separators. Support the use of multi-level address formats, such as `sub1/sub2/repo`."
  type        = string
}

variable "namespace_name" {
  description = "(required) - Name of the TCR namespace."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_tcr_repository" "this" {
  brief_desc     = var.brief_desc
  description    = var.description
  instance_id    = var.instance_id
  name           = var.name
  namespace_name = var.namespace_name
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_tcr_repository.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_tcr_repository.this.id
}

output "is_public" {
  description = "returns a bool"
  value       = tencentcloud_tcr_repository.this.is_public
}

output "update_time" {
  description = "returns a string"
  value       = tencentcloud_tcr_repository.this.update_time
}

output "url" {
  description = "returns a string"
  value       = tencentcloud_tcr_repository.this.url
}

output "this" {
  value = tencentcloud_tcr_repository.this
}
```

[top](#index)