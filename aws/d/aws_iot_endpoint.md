# aws_iot_endpoint

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
module "aws_iot_endpoint" {
  source = "./modules/aws/d/aws_iot_endpoint"

  # endpoint_type - (optional) is a type of string
  endpoint_type = null
}
```

[top](#index)

### Variables

```terraform
variable "endpoint_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_iot_endpoint" "this" {
  # endpoint_type - (optional) is a type of string
  endpoint_type = var.endpoint_type
}
```

[top](#index)

### Outputs

```terraform
output "endpoint_address" {
  description = "returns a string"
  value       = data.aws_iot_endpoint.this.endpoint_address
}

output "id" {
  description = "returns a string"
  value       = data.aws_iot_endpoint.this.id
}

output "this" {
  value = aws_iot_endpoint.this
}
```

[top](#index)