# aws_guardduty_invite_accepter

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
module "aws_guardduty_invite_accepter" {
  source = "./modules/aws/r/aws_guardduty_invite_accepter"

  # detector_id - (required) is a type of string
  detector_id = null
  # master_account_id - (required) is a type of string
  master_account_id = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "detector_id" {
  description = "(required)"
  type        = string
}

variable "master_account_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_guardduty_invite_accepter" "this" {
  detector_id       = var.detector_id
  master_account_id = var.master_account_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_guardduty_invite_accepter.this.id
}

output "this" {
  value = aws_guardduty_invite_accepter.this
}
```

[top](#index)