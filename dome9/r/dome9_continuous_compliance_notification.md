# dome9_continuous_compliance_notification

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.21.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_continuous_compliance_notification" {
  source = "./modules/dome9/r/dome9_continuous_compliance_notification"

  # alerts_console - (optional) is a type of bool
  alerts_console = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null

  change_detection = [{
    aws_security_hub_integration = [{
      external_account_id = null
      region              = null
    }]
    aws_security_hub_integration_state = null
    email_data = [{
      recipients = []
    }]
    email_per_finding_data = [{
      notification_output_format = null
      recipients                 = []
    }]
    email_per_finding_sending_state = null
    email_sending_state             = null
    external_ticket_creating_state  = null
    sns_data = [{
      sns_output_format = null
      sns_topic_arn     = null
    }]
    sns_sending_state = null
    ticketing_system_data = [{
      domain               = null
      issue_type           = null
      pass                 = null
      project_key          = null
      should_close_tickets = null
      system_type          = null
      user                 = null
    }]
    webhook_data = [{
      auth_method = null
      format_type = null
      http_method = null
      password    = null
      url         = null
      username    = null
    }]
    webhook_integration_state = null
  }]

  gcp_security_command_center_integration = [{
    project_id = null
    source_id  = null
    state      = null
  }]

  scheduled_report = [{
    email_sending_state = null
    schedule_data = [{
      cron_expression = null
      recipients      = []
      type            = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "alerts_console" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "change_detection" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      aws_security_hub_integration = set(object(
        {
          external_account_id = string
          region              = string
        }
      ))
      aws_security_hub_integration_state = string
      email_data = set(object(
        {
          recipients = list(string)
        }
      ))
      email_per_finding_data = set(object(
        {
          notification_output_format = string
          recipients                 = list(string)
        }
      ))
      email_per_finding_sending_state = string
      email_sending_state             = string
      external_ticket_creating_state  = string
      sns_data = set(object(
        {
          sns_output_format = string
          sns_topic_arn     = string
        }
      ))
      sns_sending_state = string
      ticketing_system_data = set(object(
        {
          domain               = string
          issue_type           = string
          pass                 = string
          project_key          = string
          should_close_tickets = bool
          system_type          = string
          user                 = string
        }
      ))
      webhook_data = set(object(
        {
          auth_method = string
          format_type = string
          http_method = string
          password    = string
          url         = string
          username    = string
        }
      ))
      webhook_integration_state = string
    }
  ))
}

variable "gcp_security_command_center_integration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      project_id = string
      source_id  = string
      state      = string
    }
  ))
  default = []
}

variable "scheduled_report" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      email_sending_state = string
      schedule_data = set(object(
        {
          cron_expression = string
          recipients      = list(string)
          type            = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "dome9_continuous_compliance_notification" "this" {
  alerts_console = var.alerts_console
  description    = var.description
  name           = var.name

  dynamic "change_detection" {
    for_each = var.change_detection
    content {
      aws_security_hub_integration_state = change_detection.value["aws_security_hub_integration_state"]
      email_per_finding_sending_state    = change_detection.value["email_per_finding_sending_state"]
      email_sending_state                = change_detection.value["email_sending_state"]
      external_ticket_creating_state     = change_detection.value["external_ticket_creating_state"]
      sns_sending_state                  = change_detection.value["sns_sending_state"]
      webhook_integration_state          = change_detection.value["webhook_integration_state"]

      dynamic "aws_security_hub_integration" {
        for_each = change_detection.value.aws_security_hub_integration
        content {
          external_account_id = aws_security_hub_integration.value["external_account_id"]
          region              = aws_security_hub_integration.value["region"]
        }
      }

      dynamic "email_data" {
        for_each = change_detection.value.email_data
        content {
          recipients = email_data.value["recipients"]
        }
      }

      dynamic "email_per_finding_data" {
        for_each = change_detection.value.email_per_finding_data
        content {
          notification_output_format = email_per_finding_data.value["notification_output_format"]
          recipients                 = email_per_finding_data.value["recipients"]
        }
      }

      dynamic "sns_data" {
        for_each = change_detection.value.sns_data
        content {
          sns_output_format = sns_data.value["sns_output_format"]
          sns_topic_arn     = sns_data.value["sns_topic_arn"]
        }
      }

      dynamic "ticketing_system_data" {
        for_each = change_detection.value.ticketing_system_data
        content {
          domain               = ticketing_system_data.value["domain"]
          issue_type           = ticketing_system_data.value["issue_type"]
          pass                 = ticketing_system_data.value["pass"]
          project_key          = ticketing_system_data.value["project_key"]
          should_close_tickets = ticketing_system_data.value["should_close_tickets"]
          system_type          = ticketing_system_data.value["system_type"]
          user                 = ticketing_system_data.value["user"]
        }
      }

      dynamic "webhook_data" {
        for_each = change_detection.value.webhook_data
        content {
          auth_method = webhook_data.value["auth_method"]
          format_type = webhook_data.value["format_type"]
          http_method = webhook_data.value["http_method"]
          password    = webhook_data.value["password"]
          url         = webhook_data.value["url"]
          username    = webhook_data.value["username"]
        }
      }

    }
  }

  dynamic "gcp_security_command_center_integration" {
    for_each = var.gcp_security_command_center_integration
    content {
      project_id = gcp_security_command_center_integration.value["project_id"]
      source_id  = gcp_security_command_center_integration.value["source_id"]
      state      = gcp_security_command_center_integration.value["state"]
    }
  }

  dynamic "scheduled_report" {
    for_each = var.scheduled_report
    content {
      email_sending_state = scheduled_report.value["email_sending_state"]

      dynamic "schedule_data" {
        for_each = scheduled_report.value.schedule_data
        content {
          cron_expression = schedule_data.value["cron_expression"]
          recipients      = schedule_data.value["recipients"]
          type            = schedule_data.value["type"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "alerts_console" {
  description = "returns a bool"
  value       = dome9_continuous_compliance_notification.this.alerts_console
}

output "description" {
  description = "returns a string"
  value       = dome9_continuous_compliance_notification.this.description
}

output "id" {
  description = "returns a string"
  value       = dome9_continuous_compliance_notification.this.id
}

output "this" {
  value = dome9_continuous_compliance_notification.this
}
```

[top](#index)