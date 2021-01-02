# aws_media_convert_queue

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_media_convert_queue" {
  source = "./modules/aws/r/aws_media_convert_queue"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # pricing_plan - (optional) is a type of string
  pricing_plan = null
  # status - (optional) is a type of string
  status = null
  # tags - (optional) is a type of map of string
  tags = {}

  reservation_plan_settings = [{
    commitment     = null
    renewal_type   = null
    reserved_slots = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "pricing_plan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "reservation_plan_settings" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      commitment     = string
      renewal_type   = string
      reserved_slots = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_media_convert_queue" "this" {
  description  = var.description
  name         = var.name
  pricing_plan = var.pricing_plan
  status       = var.status
  tags         = var.tags

  dynamic "reservation_plan_settings" {
    for_each = var.reservation_plan_settings
    content {
      commitment     = reservation_plan_settings.value["commitment"]
      renewal_type   = reservation_plan_settings.value["renewal_type"]
      reserved_slots = reservation_plan_settings.value["reserved_slots"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_media_convert_queue.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_media_convert_queue.this.id
}

output "this" {
  value = aws_media_convert_queue.this
}
```

[top](#index)