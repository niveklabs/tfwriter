# alicloud_ros_template

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
module "alicloud_ros_template" {
  source = "./modules/alicloud/r/alicloud_ros_template"

  # description - (optional) is a type of string
  description = null
  # tags - (optional) is a type of map of string
  tags = {}
  # template_body - (optional) is a type of string
  template_body = null
  # template_name - (required) is a type of string
  template_name = null
  # template_url - (optional) is a type of string
  template_url = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "template_body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_name" {
  description = "(required)"
  type        = string
}

variable "template_url" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ros_template" "this" {
  description   = var.description
  tags          = var.tags
  template_body = var.template_body
  template_name = var.template_name
  template_url  = var.template_url
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ros_template.this.id
}

output "this" {
  value = alicloud_ros_template.this
}
```

[top](#index)