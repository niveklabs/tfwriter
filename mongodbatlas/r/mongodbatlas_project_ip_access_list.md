# mongodbatlas_project_ip_access_list

[back](../mongodbatlas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mongodbatlas = ">= 0.8.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mongodbatlas_project_ip_access_list" {
  source = "./modules/mongodbatlas/r/mongodbatlas_project_ip_access_list"

  # aws_security_group - (optional) is a type of string
  aws_security_group = null
  # cidr_block - (optional) is a type of string
  cidr_block = null
  # comment - (optional) is a type of string
  comment = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # project_id - (required) is a type of string
  project_id = null

  timeouts = [{
    delete = null
    read   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "aws_security_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      delete = string
      read   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "mongodbatlas_project_ip_access_list" "this" {
  aws_security_group = var.aws_security_group
  cidr_block         = var.cidr_block
  comment            = var.comment
  ip_address         = var.ip_address
  project_id         = var.project_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "aws_security_group" {
  description = "returns a string"
  value       = mongodbatlas_project_ip_access_list.this.aws_security_group
}

output "cidr_block" {
  description = "returns a string"
  value       = mongodbatlas_project_ip_access_list.this.cidr_block
}

output "comment" {
  description = "returns a string"
  value       = mongodbatlas_project_ip_access_list.this.comment
}

output "id" {
  description = "returns a string"
  value       = mongodbatlas_project_ip_access_list.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = mongodbatlas_project_ip_access_list.this.ip_address
}

output "this" {
  value = mongodbatlas_project_ip_access_list.this
}
```

[top](#index)