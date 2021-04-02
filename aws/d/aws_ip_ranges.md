# aws_ip_ranges

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
module "aws_ip_ranges" {
  source = "./modules/aws/d/aws_ip_ranges"

  # regions - (optional) is a type of set of string
  regions = []
  # services - (required) is a type of set of string
  services = []
  # url - (optional) is a type of string
  url = null
}
```

[top](#index)

### Variables

```terraform
variable "regions" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "services" {
  description = "(required)"
  type        = set(string)
}

variable "url" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_ip_ranges" "this" {
  regions  = var.regions
  services = var.services
  url      = var.url
}
```

[top](#index)

### Outputs

```terraform
output "cidr_blocks" {
  description = "returns a list of string"
  value       = data.aws_ip_ranges.this.cidr_blocks
}

output "create_date" {
  description = "returns a string"
  value       = data.aws_ip_ranges.this.create_date
}

output "id" {
  description = "returns a string"
  value       = data.aws_ip_ranges.this.id
}

output "ipv6_cidr_blocks" {
  description = "returns a list of string"
  value       = data.aws_ip_ranges.this.ipv6_cidr_blocks
}

output "sync_token" {
  description = "returns a number"
  value       = data.aws_ip_ranges.this.sync_token
}

output "this" {
  value = aws_ip_ranges.this
}
```

[top](#index)