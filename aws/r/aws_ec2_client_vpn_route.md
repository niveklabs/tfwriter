# aws_ec2_client_vpn_route

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
module "aws_ec2_client_vpn_route" {
  source = "./modules/aws/r/aws_ec2_client_vpn_route"

  # client_vpn_endpoint_id - (required) is a type of string
  client_vpn_endpoint_id = null
  # description - (optional) is a type of string
  description = null
  # destination_cidr_block - (required) is a type of string
  destination_cidr_block = null
  # target_vpc_subnet_id - (required) is a type of string
  target_vpc_subnet_id = null
}
```

[top](#index)

### Variables

```hcl
variable "client_vpn_endpoint_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_cidr_block" {
  description = "(required)"
  type        = string
}

variable "target_vpc_subnet_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_ec2_client_vpn_route" "this" {
  client_vpn_endpoint_id = var.client_vpn_endpoint_id
  description            = var.description
  destination_cidr_block = var.destination_cidr_block
  target_vpc_subnet_id   = var.target_vpc_subnet_id
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_ec2_client_vpn_route.this.id
}

output "origin" {
  description = "returns a string"
  value       = aws_ec2_client_vpn_route.this.origin
}

output "type" {
  description = "returns a string"
  value       = aws_ec2_client_vpn_route.this.type
}

output "this" {
  value = aws_ec2_client_vpn_route.this
}
```

[top](#index)