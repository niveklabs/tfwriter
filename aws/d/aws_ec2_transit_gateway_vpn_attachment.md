# aws_ec2_transit_gateway_vpn_attachment

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
module "aws_ec2_transit_gateway_vpn_attachment" {
  source = "./modules/aws/d/aws_ec2_transit_gateway_vpn_attachment"

  # tags - (optional) is a type of map of string
  tags = {}
  # transit_gateway_id - (optional) is a type of string
  transit_gateway_id = null
  # vpn_connection_id - (optional) is a type of string
  vpn_connection_id = null

  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```hcl
variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "transit_gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpn_connection_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
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

```hcl
data "aws_ec2_transit_gateway_vpn_attachment" "this" {
  tags               = var.tags
  transit_gateway_id = var.transit_gateway_id
  vpn_connection_id  = var.vpn_connection_id

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

```hcl
output "id" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway_vpn_attachment.this.id
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_ec2_transit_gateway_vpn_attachment.this.tags
}

output "this" {
  value = aws_ec2_transit_gateway_vpn_attachment.this
}
```

[top](#index)