# aws_vpc_endpoint_service

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_vpc_endpoint_service" {
  source = "./modules/aws/r/aws_vpc_endpoint_service"

  # acceptance_required - (required) is a type of bool
  acceptance_required = null
  # allowed_principals - (optional) is a type of set of string
  allowed_principals = []
  # gateway_load_balancer_arns - (optional) is a type of set of string
  gateway_load_balancer_arns = []
  # network_load_balancer_arns - (optional) is a type of set of string
  network_load_balancer_arns = []
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```hcl
variable "acceptance_required" {
  description = "(required)"
  type        = bool
}

variable "allowed_principals" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "gateway_load_balancer_arns" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "network_load_balancer_arns" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_vpc_endpoint_service" "this" {
  acceptance_required        = var.acceptance_required
  allowed_principals         = var.allowed_principals
  gateway_load_balancer_arns = var.gateway_load_balancer_arns
  network_load_balancer_arns = var.network_load_balancer_arns
  tags                       = var.tags
}
```

[top](#index)

### Outputs

```hcl
output "allowed_principals" {
  description = "returns a set of string"
  value       = aws_vpc_endpoint_service.this.allowed_principals
}

output "arn" {
  description = "returns a string"
  value       = aws_vpc_endpoint_service.this.arn
}

output "availability_zones" {
  description = "returns a set of string"
  value       = aws_vpc_endpoint_service.this.availability_zones
}

output "base_endpoint_dns_names" {
  description = "returns a set of string"
  value       = aws_vpc_endpoint_service.this.base_endpoint_dns_names
}

output "id" {
  description = "returns a string"
  value       = aws_vpc_endpoint_service.this.id
}

output "manages_vpc_endpoints" {
  description = "returns a bool"
  value       = aws_vpc_endpoint_service.this.manages_vpc_endpoints
}

output "private_dns_name" {
  description = "returns a string"
  value       = aws_vpc_endpoint_service.this.private_dns_name
}

output "service_name" {
  description = "returns a string"
  value       = aws_vpc_endpoint_service.this.service_name
}

output "service_type" {
  description = "returns a string"
  value       = aws_vpc_endpoint_service.this.service_type
}

output "state" {
  description = "returns a string"
  value       = aws_vpc_endpoint_service.this.state
}

output "this" {
  value = aws_vpc_endpoint_service.this
}
```

[top](#index)