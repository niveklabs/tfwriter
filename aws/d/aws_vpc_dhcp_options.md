# aws_vpc_dhcp_options

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
module "aws_vpc_dhcp_options" {
  source = "./modules/aws/d/aws_vpc_dhcp_options"

  # dhcp_options_id - (optional) is a type of string
  dhcp_options_id = null
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
variable "dhcp_options_id" {
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
      values = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aws_vpc_dhcp_options" "this" {
  dhcp_options_id = var.dhcp_options_id
  tags            = var.tags

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
output "arn" {
  description = "returns a string"
  value       = data.aws_vpc_dhcp_options.this.arn
}

output "dhcp_options_id" {
  description = "returns a string"
  value       = data.aws_vpc_dhcp_options.this.dhcp_options_id
}

output "domain_name" {
  description = "returns a string"
  value       = data.aws_vpc_dhcp_options.this.domain_name
}

output "domain_name_servers" {
  description = "returns a list of string"
  value       = data.aws_vpc_dhcp_options.this.domain_name_servers
}

output "id" {
  description = "returns a string"
  value       = data.aws_vpc_dhcp_options.this.id
}

output "netbios_name_servers" {
  description = "returns a list of string"
  value       = data.aws_vpc_dhcp_options.this.netbios_name_servers
}

output "netbios_node_type" {
  description = "returns a string"
  value       = data.aws_vpc_dhcp_options.this.netbios_node_type
}

output "ntp_servers" {
  description = "returns a list of string"
  value       = data.aws_vpc_dhcp_options.this.ntp_servers
}

output "owner_id" {
  description = "returns a string"
  value       = data.aws_vpc_dhcp_options.this.owner_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_vpc_dhcp_options.this.tags
}

output "this" {
  value = aws_vpc_dhcp_options.this
}
```

[top](#index)