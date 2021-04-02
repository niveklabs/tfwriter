# aws_guardduty_member

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
module "aws_guardduty_member" {
  source = "./modules/aws/r/aws_guardduty_member"

  # account_id - (required) is a type of string
  account_id = null
  # detector_id - (required) is a type of string
  detector_id = null
  # disable_email_notification - (optional) is a type of bool
  disable_email_notification = null
  # email - (required) is a type of string
  email = null
  # invitation_message - (optional) is a type of string
  invitation_message = null
  # invite - (optional) is a type of bool
  invite = null

  timeouts = [{
    create = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(required)"
  type        = string
}

variable "detector_id" {
  description = "(required)"
  type        = string
}

variable "disable_email_notification" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "invitation_message" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "invite" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_guardduty_member" "this" {
  account_id                 = var.account_id
  detector_id                = var.detector_id
  disable_email_notification = var.disable_email_notification
  email                      = var.email
  invitation_message         = var.invitation_message
  invite                     = var.invite

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_guardduty_member.this.id
}

output "relationship_status" {
  description = "returns a string"
  value       = aws_guardduty_member.this.relationship_status
}

output "this" {
  value = aws_guardduty_member.this
}
```

[top](#index)