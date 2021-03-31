# alicloud_api_gateway_app

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
module "alicloud_api_gateway_app" {
  source = "./modules/alicloud/r/alicloud_api_gateway_app"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_api_gateway_app" "this" {
  description = var.description
  name        = var.name
  tags        = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_api_gateway_app.this.id
}

output "this" {
  value = alicloud_api_gateway_app.this
}
```

[top](#index)