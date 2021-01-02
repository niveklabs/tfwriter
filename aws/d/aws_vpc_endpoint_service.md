# aws_vpc_endpoint_service

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_vpc_endpoint_service" {
  source = "./modules/aws/d/aws_vpc_endpoint_service"

  # service - (optional) is a type of string
  service = null
  # service_name - (optional) is a type of string
  service_name = null
  # service_type - (optional) is a type of string
  service_type = null
  # tags - (optional) is a type of map of string
  tags = {}

  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aws_vpc_endpoint_service" "this" {
  service      = var.service
  service_name = var.service_name
  service_type = var.service_type
  tags         = var.tags

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "acceptance_required" {
  description = "returns a bool"
  value       = data.aws_vpc_endpoint_service.this.acceptance_required
}

output "arn" {
  description = "returns a string"
  value       = data.aws_vpc_endpoint_service.this.arn
}

output "availability_zones" {
  description = "returns a set of string"
  value       = data.aws_vpc_endpoint_service.this.availability_zones
}

output "base_endpoint_dns_names" {
  description = "returns a set of string"
  value       = data.aws_vpc_endpoint_service.this.base_endpoint_dns_names
}

output "id" {
  description = "returns a string"
  value       = data.aws_vpc_endpoint_service.this.id
}

output "manages_vpc_endpoints" {
  description = "returns a bool"
  value       = data.aws_vpc_endpoint_service.this.manages_vpc_endpoints
}

output "owner" {
  description = "returns a string"
  value       = data.aws_vpc_endpoint_service.this.owner
}

output "private_dns_name" {
  description = "returns a string"
  value       = data.aws_vpc_endpoint_service.this.private_dns_name
}

output "service_id" {
  description = "returns a string"
  value       = data.aws_vpc_endpoint_service.this.service_id
}

output "service_name" {
  description = "returns a string"
  value       = data.aws_vpc_endpoint_service.this.service_name
}

output "service_type" {
  description = "returns a string"
  value       = data.aws_vpc_endpoint_service.this.service_type
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_vpc_endpoint_service.this.tags
}

output "vpc_endpoint_policy_supported" {
  description = "returns a bool"
  value       = data.aws_vpc_endpoint_service.this.vpc_endpoint_policy_supported
}

output "this" {
  value = aws_vpc_endpoint_service.this
}
```

[top](#index)