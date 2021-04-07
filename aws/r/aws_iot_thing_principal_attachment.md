# aws_iot_thing_principal_attachment

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_iot_thing_principal_attachment" {
  source = "./modules/aws/r/aws_iot_thing_principal_attachment"

  # principal - (required) is a type of string
  principal = null
  # thing - (required) is a type of string
  thing = null
}
```

[top](#index)

### Variables

```terraform
variable "principal" {
  description = "(required)"
  type        = string
}

variable "thing" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_iot_thing_principal_attachment" "this" {
  # principal - (required) is a type of string
  principal = var.principal
  # thing - (required) is a type of string
  thing = var.thing
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_iot_thing_principal_attachment.this.id
}

output "this" {
  value = aws_iot_thing_principal_attachment.this
}
```

[top](#index)