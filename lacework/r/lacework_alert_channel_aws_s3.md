# lacework_alert_channel_aws_s3

[back](../lacework.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    lacework = ">= 0.3.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "lacework_alert_channel_aws_s3" {
  source = "./modules/lacework/r/lacework_alert_channel_aws_s3"

  # bucket_arn - (required) is a type of string
  bucket_arn = null
  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null

  credentials = [{
    external_id = null
    role_arn    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "bucket_arn" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "credentials" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      external_id = string
      role_arn    = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "lacework_alert_channel_aws_s3" "this" {
  # bucket_arn - (required) is a type of string
  bucket_arn = var.bucket_arn
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # name - (required) is a type of string
  name = var.name

  dynamic "credentials" {
    for_each = var.credentials
    content {
      # external_id - (required) is a type of string
      external_id = credentials.value["external_id"]
      # role_arn - (required) is a type of string
      role_arn = credentials.value["role_arn"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_alert_channel_aws_s3.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_alert_channel_aws_s3.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_alert_channel_aws_s3.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_alert_channel_aws_s3.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_alert_channel_aws_s3.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_alert_channel_aws_s3.this.type_name
}

output "this" {
  value = lacework_alert_channel_aws_s3.this
}
```

[top](#index)