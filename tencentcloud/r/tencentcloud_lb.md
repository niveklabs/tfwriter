# tencentcloud_lb

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
module "tencentcloud_lb" {
  source = "./modules/tencentcloud/r/tencentcloud_lb"

  # forward - (optional) is a type of string
  forward = null
  # name - (optional) is a type of string
  name = null
  # project_id - (optional) is a type of number
  project_id = null
  # type - (required) is a type of string
  type = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "forward" {
  description = "(optional) - The type of the LB. Valid value: 'CLASSIC', 'APPLICATION'."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - The name of the LB."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - The project id of the LB, unspecified or 0 stands for default project."
  type        = number
  default     = null
}

variable "type" {
  description = "(required) - The network type of the LB. Valid value: 'OPEN', 'INTERNAL'."
  type        = string
}

variable "vpc_id" {
  description = "(optional) - The VPC ID of the LB, unspecified or 0 stands for CVM basic network."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_lb" "this" {
  forward    = var.forward
  name       = var.name
  project_id = var.project_id
  type       = var.type
  vpc_id     = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "forward" {
  description = "returns a string"
  value       = tencentcloud_lb.this.forward
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_lb.this.id
}

output "name" {
  description = "returns a string"
  value       = tencentcloud_lb.this.name
}

output "project_id" {
  description = "returns a number"
  value       = tencentcloud_lb.this.project_id
}

output "status" {
  description = "returns a string"
  value       = tencentcloud_lb.this.status
}

output "vpc_id" {
  description = "returns a string"
  value       = tencentcloud_lb.this.vpc_id
}

output "this" {
  value = tencentcloud_lb.this
}
```

[top](#index)