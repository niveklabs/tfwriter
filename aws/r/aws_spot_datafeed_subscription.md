# aws_spot_datafeed_subscription

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
module "aws_spot_datafeed_subscription" {
  source = "./modules/aws/r/aws_spot_datafeed_subscription"

  # bucket - (required) is a type of string
  bucket = null
  # prefix - (optional) is a type of string
  prefix = null
}
```

[top](#index)

### Variables

```hcl
variable "bucket" {
  description = "(required)"
  type        = string
}

variable "prefix" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_spot_datafeed_subscription" "this" {
  bucket = var.bucket
  prefix = var.prefix
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_spot_datafeed_subscription.this.id
}

output "this" {
  value = aws_spot_datafeed_subscription.this
}
```

[top](#index)