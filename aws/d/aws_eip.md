# aws_eip

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
module "aws_eip" {
  source = "./modules/aws/d/aws_eip"

  # public_ip - (optional) is a type of string
  public_ip = null
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
variable "public_ip" {
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
data "aws_eip" "this" {
  public_ip = var.public_ip
  tags      = var.tags

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
output "association_id" {
  description = "returns a string"
  value       = data.aws_eip.this.association_id
}

output "carrier_ip" {
  description = "returns a string"
  value       = data.aws_eip.this.carrier_ip
}

output "customer_owned_ip" {
  description = "returns a string"
  value       = data.aws_eip.this.customer_owned_ip
}

output "customer_owned_ipv4_pool" {
  description = "returns a string"
  value       = data.aws_eip.this.customer_owned_ipv4_pool
}

output "domain" {
  description = "returns a string"
  value       = data.aws_eip.this.domain
}

output "id" {
  description = "returns a string"
  value       = data.aws_eip.this.id
}

output "instance_id" {
  description = "returns a string"
  value       = data.aws_eip.this.instance_id
}

output "network_interface_id" {
  description = "returns a string"
  value       = data.aws_eip.this.network_interface_id
}

output "network_interface_owner_id" {
  description = "returns a string"
  value       = data.aws_eip.this.network_interface_owner_id
}

output "private_dns" {
  description = "returns a string"
  value       = data.aws_eip.this.private_dns
}

output "private_ip" {
  description = "returns a string"
  value       = data.aws_eip.this.private_ip
}

output "public_dns" {
  description = "returns a string"
  value       = data.aws_eip.this.public_dns
}

output "public_ip" {
  description = "returns a string"
  value       = data.aws_eip.this.public_ip
}

output "public_ipv4_pool" {
  description = "returns a string"
  value       = data.aws_eip.this.public_ipv4_pool
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_eip.this.tags
}

output "this" {
  value = aws_eip.this
}
```

[top](#index)