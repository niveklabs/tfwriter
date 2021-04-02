# aws_securityhub_invite_accepter

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
module "aws_securityhub_invite_accepter" {
  source = "./modules/aws/r/aws_securityhub_invite_accepter"

  # master_id - (required) is a type of string
  master_id = null
}
```

[top](#index)

### Variables

```terraform
variable "master_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_securityhub_invite_accepter" "this" {
  master_id = var.master_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_securityhub_invite_accepter.this.id
}

output "invitation_id" {
  description = "returns a string"
  value       = aws_securityhub_invite_accepter.this.invitation_id
}

output "this" {
  value = aws_securityhub_invite_accepter.this
}
```

[top](#index)