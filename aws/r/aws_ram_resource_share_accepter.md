# aws_ram_resource_share_accepter

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
module "aws_ram_resource_share_accepter" {
  source = "./modules/aws/r/aws_ram_resource_share_accepter"

  # share_arn - (required) is a type of string
  share_arn = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "share_arn" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_ram_resource_share_accepter" "this" {
  share_arn = var.share_arn

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_ram_resource_share_accepter.this.id
}

output "invitation_arn" {
  description = "returns a string"
  value       = aws_ram_resource_share_accepter.this.invitation_arn
}

output "receiver_account_id" {
  description = "returns a string"
  value       = aws_ram_resource_share_accepter.this.receiver_account_id
}

output "resources" {
  description = "returns a list of string"
  value       = aws_ram_resource_share_accepter.this.resources
}

output "sender_account_id" {
  description = "returns a string"
  value       = aws_ram_resource_share_accepter.this.sender_account_id
}

output "share_id" {
  description = "returns a string"
  value       = aws_ram_resource_share_accepter.this.share_id
}

output "share_name" {
  description = "returns a string"
  value       = aws_ram_resource_share_accepter.this.share_name
}

output "status" {
  description = "returns a string"
  value       = aws_ram_resource_share_accepter.this.status
}

output "this" {
  value = aws_ram_resource_share_accepter.this
}
```

[top](#index)