# mongodbatlas_project_ip_whitelist

[back](../mongodbatlas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "mongodbatlas_project_ip_whitelist" {
  source = "./modules/mongodbatlas/d/mongodbatlas_project_ip_whitelist"

  # aws_security_group - (optional) is a type of string
  aws_security_group = null
  # cidr_block - (optional) is a type of string
  cidr_block = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # project_id - (required) is a type of string
  project_id = null
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

variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "mongodbatlas_project_ip_whitelist" "this" {
  aws_security_group = var.aws_security_group
  cidr_block         = var.cidr_block
  ip_address         = var.ip_address
  project_id         = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "aws_security_group" {
  description = "returns a string"
  value       = data.mongodbatlas_project_ip_whitelist.this.aws_security_group
}

output "cidr_block" {
  description = "returns a string"
  value       = data.mongodbatlas_project_ip_whitelist.this.cidr_block
}

output "comment" {
  description = "returns a string"
  value       = data.mongodbatlas_project_ip_whitelist.this.comment
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_project_ip_whitelist.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = data.mongodbatlas_project_ip_whitelist.this.ip_address
}

output "this" {
  value = mongodbatlas_project_ip_whitelist.this
}
```

[top](#index)