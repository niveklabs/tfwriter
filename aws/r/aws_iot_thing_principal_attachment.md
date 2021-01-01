# aws_iot_thing_principal_attachment

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

```hcl
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

```hcl
resource "aws_iot_thing_principal_attachment" "this" {
  principal = var.principal
  thing     = var.thing
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_iot_thing_principal_attachment.this.id
}

output "this" {
  value = aws_iot_thing_principal_attachment.this
}
```

[top](#index)