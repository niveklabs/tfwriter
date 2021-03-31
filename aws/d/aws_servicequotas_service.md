# aws_servicequotas_service

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_servicequotas_service" {
  source = "./modules/aws/d/aws_servicequotas_service"

  # service_name - (required) is a type of string
  service_name = null
}
```

[top](#index)

### Variables

```terraform
variable "service_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_servicequotas_service" "this" {
  service_name = var.service_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_servicequotas_service.this.id
}

output "service_code" {
  description = "returns a string"
  value       = data.aws_servicequotas_service.this.service_code
}

output "this" {
  value = aws_servicequotas_service.this
}
```

[top](#index)