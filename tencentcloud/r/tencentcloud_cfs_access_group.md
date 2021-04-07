# tencentcloud_cfs_access_group

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
module "tencentcloud_cfs_access_group" {
  source = "./modules/tencentcloud/r/tencentcloud_cfs_access_group"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the access group, and max length is 255."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the access group, and max length is 64."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cfs_access_group" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_cfs_access_group.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_cfs_access_group.this.id
}

output "this" {
  value = tencentcloud_cfs_access_group.this
}
```

[top](#index)