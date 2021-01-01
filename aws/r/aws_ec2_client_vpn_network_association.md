# aws_ec2_client_vpn_network_association

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_ec2_client_vpn_network_association" {
  source = "./modules/aws/r/aws_ec2_client_vpn_network_association"

  # client_vpn_endpoint_id - (required) is a type of string
  client_vpn_endpoint_id = null
  # security_groups - (optional) is a type of set of string
  security_groups = []
  # subnet_id - (required) is a type of string
  subnet_id = null
}
```

[top](#index)

### Variables

```hcl
variable "client_vpn_endpoint_id" {
  description = "(required)"
  type        = string
}

variable "security_groups" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "subnet_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_ec2_client_vpn_network_association" "this" {
  client_vpn_endpoint_id = var.client_vpn_endpoint_id
  security_groups        = var.security_groups
  subnet_id              = var.subnet_id
}
```

[top](#index)

### Outputs

```hcl
output "association_id" {
  description = "returns a string"
  value       = aws_ec2_client_vpn_network_association.this.association_id
}

output "id" {
  description = "returns a string"
  value       = aws_ec2_client_vpn_network_association.this.id
}

output "security_groups" {
  description = "returns a set of string"
  value       = aws_ec2_client_vpn_network_association.this.security_groups
}

output "status" {
  description = "returns a string"
  value       = aws_ec2_client_vpn_network_association.this.status
}

output "vpc_id" {
  description = "returns a string"
  value       = aws_ec2_client_vpn_network_association.this.vpc_id
}

output "this" {
  value = aws_ec2_client_vpn_network_association.this
}
```

[top](#index)