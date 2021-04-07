# aws_guardduty_invite_accepter

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

```terraform
variable "detector_id" {
  description = "(required)"
  type        = string
}

variable "master_account_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
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

```terraform
resource "aws_guardduty_invite_accepter" "this" {
  # detector_id - (required) is a type of string
  detector_id = var.detector_id
  # master_account_id - (required) is a type of string
  master_account_id = var.master_account_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_guardduty_invite_accepter.this.id
}

output "this" {
  value = aws_guardduty_invite_accepter.this
}
```

[top](#index)