# aws_dx_gateway

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
module "aws_dx_gateway" {
  source = "./modules/aws/d/aws_dx_gateway"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_dx_gateway" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "amazon_side_asn" {
  description = "returns a string"
  value       = data.aws_dx_gateway.this.amazon_side_asn
}

output "id" {
  description = "returns a string"
  value       = data.aws_dx_gateway.this.id
}

output "owner_account_id" {
  description = "returns a string"
  value       = data.aws_dx_gateway.this.owner_account_id
}

output "this" {
  value = aws_dx_gateway.this
}
```

[top](#index)