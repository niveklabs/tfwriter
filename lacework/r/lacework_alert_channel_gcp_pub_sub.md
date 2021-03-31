# lacework_alert_channel_gcp_pub_sub

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
module "lacework_alert_channel_gcp_pub_sub" {
  source = "./modules/lacework/r/lacework_alert_channel_gcp_pub_sub"

  # enabled - (optional) is a type of bool
  enabled = null
  # issue_grouping - (optional) is a type of string
  issue_grouping = null
  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
  # topic_id - (required) is a type of string
  topic_id = null

  credentials = [{
    client_email   = null
    client_id      = null
    private_key    = null
    private_key_id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "issue_grouping" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "topic_id" {
  description = "(required)"
  type        = string
}

variable "credentials" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      client_email   = string
      client_id      = string
      private_key    = string
      private_key_id = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "lacework_alert_channel_gcp_pub_sub" "this" {
  enabled        = var.enabled
  issue_grouping = var.issue_grouping
  name           = var.name
  project_id     = var.project_id
  topic_id       = var.topic_id

  dynamic "credentials" {
    for_each = var.credentials
    content {
      client_email   = credentials.value["client_email"]
      client_id      = credentials.value["client_id"]
      private_key    = credentials.value["private_key"]
      private_key_id = credentials.value["private_key_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_alert_channel_gcp_pub_sub.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_alert_channel_gcp_pub_sub.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_alert_channel_gcp_pub_sub.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_alert_channel_gcp_pub_sub.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_alert_channel_gcp_pub_sub.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_alert_channel_gcp_pub_sub.this.type_name
}

output "this" {
  value = lacework_alert_channel_gcp_pub_sub.this
}
```

[top](#index)