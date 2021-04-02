# aws_elb_attachment

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
module "aws_elb_attachment" {
  source = "./modules/aws/r/aws_elb_attachment"

  # elb - (required) is a type of string
  elb = null
  # instance - (required) is a type of string
  instance = null
}
```

[top](#index)

### Variables

```terraform
variable "elb" {
  description = "(required)"
  type        = string
}

variable "instance" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_elb_attachment" "this" {
  elb      = var.elb
  instance = var.instance
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_elb_attachment.this.id
}

output "this" {
  value = aws_elb_attachment.this
}
```

[top](#index)