# tencentcloud_security_group

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
module "tencentcloud_security_group" {
  source = "./modules/tencentcloud/r/tencentcloud_security_group"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # project_id - (optional) is a type of number
  project_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the security group."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the security group to be queried."
  type        = string
}

variable "project_id" {
  description = "(optional) - Project ID of the security group."
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional) - Tags of the security group."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_security_group" "this" {
  description = var.description
  name        = var.name
  project_id  = var.project_id
  tags        = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_security_group.this.id
}

output "project_id" {
  description = "returns a number"
  value       = tencentcloud_security_group.this.project_id
}

output "this" {
  value = tencentcloud_security_group.this
}
```

[top](#index)