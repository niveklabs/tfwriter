# aws_ec2_transit_gateway_peering_attachment

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
module "aws_ec2_transit_gateway_peering_attachment" {
  source = "./modules/aws/d/aws_ec2_transit_gateway_peering_attachment"

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

```hcl
variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "filter" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
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

```hcl
data "aws_ec2_transit_gateway_peering_attachment" "this" {
  tags = var.tags

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
  value       = data.aws_ec2_transit_gateway_peering_attachment.this.id
}

output "peer_account_id" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway_peering_attachment.this.peer_account_id
}

output "peer_region" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway_peering_attachment.this.peer_region
}

output "peer_transit_gateway_id" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway_peering_attachment.this.peer_transit_gateway_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_ec2_transit_gateway_peering_attachment.this.tags
}

output "transit_gateway_id" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway_peering_attachment.this.transit_gateway_id
}

output "this" {
  value = aws_ec2_transit_gateway_peering_attachment.this
}
```

[top](#index)