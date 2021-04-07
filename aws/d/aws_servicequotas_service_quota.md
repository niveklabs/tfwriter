# aws_servicequotas_service_quota

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_servicequotas_service_quota" {
  source = "./modules/aws/d/aws_servicequotas_service_quota"

  # quota_code - (optional) is a type of string
  quota_code = null
  # quota_name - (optional) is a type of string
  quota_name = null
  # service_code - (required) is a type of string
  service_code = null
}
```

[top](#index)

### Variables

```terraform
variable "quota_code" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "quota_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_code" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_servicequotas_service_quota" "this" {
  # quota_code - (optional) is a type of string
  quota_code = var.quota_code
  # quota_name - (optional) is a type of string
  quota_name = var.quota_name
  # service_code - (required) is a type of string
  service_code = var.service_code
}
```

[top](#index)

### Outputs

```terraform
output "adjustable" {
  description = "returns a bool"
  value       = data.aws_servicequotas_service_quota.this.adjustable
}

output "arn" {
  description = "returns a string"
  value       = data.aws_servicequotas_service_quota.this.arn
}

output "default_value" {
  description = "returns a number"
  value       = data.aws_servicequotas_service_quota.this.default_value
}

output "global_quota" {
  description = "returns a bool"
  value       = data.aws_servicequotas_service_quota.this.global_quota
}

output "id" {
  description = "returns a string"
  value       = data.aws_servicequotas_service_quota.this.id
}

output "quota_code" {
  description = "returns a string"
  value       = data.aws_servicequotas_service_quota.this.quota_code
}

output "quota_name" {
  description = "returns a string"
  value       = data.aws_servicequotas_service_quota.this.quota_name
}

output "service_name" {
  description = "returns a string"
  value       = data.aws_servicequotas_service_quota.this.service_name
}

output "value" {
  description = "returns a number"
  value       = data.aws_servicequotas_service_quota.this.value
}

output "this" {
  value = aws_servicequotas_service_quota.this
}
```

[top](#index)