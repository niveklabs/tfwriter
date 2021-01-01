# aws_vpc_dhcp_options

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
module "aws_vpc_dhcp_options" {
  source = "./modules/aws/r/aws_vpc_dhcp_options"

  # domain_name - (optional) is a type of string
  domain_name = null
  # domain_name_servers - (optional) is a type of list of string
  domain_name_servers = []
  # netbios_name_servers - (optional) is a type of list of string
  netbios_name_servers = []
  # netbios_node_type - (optional) is a type of string
  netbios_node_type = null
  # ntp_servers - (optional) is a type of list of string
  ntp_servers = []
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```hcl
variable "domain_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain_name_servers" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

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

variable "ntp_servers" {
  description = "(optional)"
  type        = list(string)
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
resource "aws_vpc_dhcp_options" "this" {
  domain_name          = var.domain_name
  domain_name_servers  = var.domain_name_servers
  netbios_name_servers = var.netbios_name_servers
  netbios_node_type    = var.netbios_node_type
  ntp_servers          = var.ntp_servers
  tags                 = var.tags
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_vpc_dhcp_options.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_vpc_dhcp_options.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_vpc_dhcp_options.this.owner_id
}

output "this" {
  value = aws_vpc_dhcp_options.this
}
```

[top](#index)