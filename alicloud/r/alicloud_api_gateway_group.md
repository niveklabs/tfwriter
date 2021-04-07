# alicloud_api_gateway_group

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
module "alicloud_api_gateway_group" {
  source = "./modules/alicloud/r/alicloud_api_gateway_group"

  # description - (required) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_api_gateway_group" "this" {
  # description - (required) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_api_gateway_group.this.id
}

output "sub_domain" {
  description = "returns a string"
  value       = alicloud_api_gateway_group.this.sub_domain
}

output "vpc_domain" {
  description = "returns a string"
  value       = alicloud_api_gateway_group.this.vpc_domain
}

output "this" {
  value = alicloud_api_gateway_group.this
}
```

[top](#index)