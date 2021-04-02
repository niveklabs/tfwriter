# aws_customer_gateway

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_customer_gateway" {
  source = "./modules/aws/r/aws_customer_gateway"

  # bgp_asn - (required) is a type of string
  bgp_asn = null
  # device_name - (optional) is a type of string
  device_name = null
  # ip_address - (required) is a type of string
  ip_address = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "bgp_asn" {
  description = "(required)"
  type        = string
}

variable "device_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_address" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_customer_gateway" "this" {
  bgp_asn     = var.bgp_asn
  device_name = var.device_name
  ip_address  = var.ip_address
  tags        = var.tags
  type        = var.type
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_customer_gateway.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_customer_gateway.this.id
}

output "this" {
  value = aws_customer_gateway.this
}
```

[top](#index)