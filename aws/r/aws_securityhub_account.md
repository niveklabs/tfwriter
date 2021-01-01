# aws_securityhub_account

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
module "aws_securityhub_account" {
  source = "./modules/aws/r/aws_securityhub_account"

}
```

[top](#index)

### Variables

```hcl
```

[top](#index)

### Resource

```hcl
resource "aws_securityhub_account" "this" {
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_securityhub_account.this.id
}

output "this" {
  value = aws_securityhub_account.this
}
```

[top](#index)