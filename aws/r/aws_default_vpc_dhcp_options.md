# aws_default_vpc_dhcp_options

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
module "aws_default_vpc_dhcp_options" {
  source = "./modules/aws/r/aws_default_vpc_dhcp_options"

  # netbios_name_servers - (optional) is a type of list of string
  netbios_name_servers = []
  # netbios_node_type - (optional) is a type of string
  netbios_node_type = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```hcl
variable "netbios_name_servers" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "netbios_node_type" {
  description = "(optional)"
  type        = string
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
resource "aws_default_vpc_dhcp_options" "this" {
  netbios_name_servers = var.netbios_name_servers
  netbios_node_type    = var.netbios_node_type
  tags                 = var.tags
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_default_vpc_dhcp_options.this.arn
}

output "domain_name" {
  description = "returns a string"
  value       = aws_default_vpc_dhcp_options.this.domain_name
}

output "domain_name_servers" {
  description = "returns a string"
  value       = aws_default_vpc_dhcp_options.this.domain_name_servers
}

output "id" {
  description = "returns a string"
  value       = aws_default_vpc_dhcp_options.this.id
}

output "ntp_servers" {
  description = "returns a string"
  value       = aws_default_vpc_dhcp_options.this.ntp_servers
}

output "owner_id" {
  description = "returns a string"
  value       = aws_default_vpc_dhcp_options.this.owner_id
}

output "this" {
  value = aws_default_vpc_dhcp_options.this
}
```

[top](#index)