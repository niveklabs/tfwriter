# aws_worklink_fleet

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
module "aws_worklink_fleet" {
  source = "./modules/aws/r/aws_worklink_fleet"

  # audit_stream_arn - (optional) is a type of string
  audit_stream_arn = null
  # device_ca_certificate - (optional) is a type of string
  device_ca_certificate = null
  # display_name - (optional) is a type of string
  display_name = null
  # name - (required) is a type of string
  name = null
  # optimize_for_end_user_location - (optional) is a type of bool
  optimize_for_end_user_location = null

  identity_provider = [{
    saml_metadata = null
    type          = null
  }]

  network = [{
    security_group_ids = []
    subnet_ids         = []
    vpc_id             = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "audit_stream_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_ca_certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "optimize_for_end_user_location" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "identity_provider" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      saml_metadata = string
      type          = string
    }
  ))
  default = []
}

variable "network" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      security_group_ids = set(string)
      subnet_ids         = set(string)
      vpc_id             = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_worklink_fleet" "this" {
  audit_stream_arn               = var.audit_stream_arn
  device_ca_certificate          = var.device_ca_certificate
  display_name                   = var.display_name
  name                           = var.name
  optimize_for_end_user_location = var.optimize_for_end_user_location

  dynamic "identity_provider" {
    for_each = var.identity_provider
    content {
      saml_metadata = identity_provider.value["saml_metadata"]
      type          = identity_provider.value["type"]
    }
  }

  dynamic "network" {
    for_each = var.network
    content {
      security_group_ids = network.value["security_group_ids"]
      subnet_ids         = network.value["subnet_ids"]
      vpc_id             = network.value["vpc_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_worklink_fleet.this.arn
}

output "company_code" {
  description = "returns a string"
  value       = aws_worklink_fleet.this.company_code
}

output "created_time" {
  description = "returns a string"
  value       = aws_worklink_fleet.this.created_time
}

output "id" {
  description = "returns a string"
  value       = aws_worklink_fleet.this.id
}

output "last_updated_time" {
  description = "returns a string"
  value       = aws_worklink_fleet.this.last_updated_time
}

output "this" {
  value = aws_worklink_fleet.this
}
```

[top](#index)