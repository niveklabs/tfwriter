# datadog_integration_slack_channel

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_integration_slack_channel" {
  source = "./modules/datadog/r/datadog_integration_slack_channel"

  # account_name - (required) is a type of string
  account_name = null
  # channel_name - (required) is a type of string
  channel_name = null

  display = [{
    message  = null
    notified = null
    snapshot = null
    tags     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(required) - Slack account name."
  type        = string
}

variable "channel_name" {
  description = "(required) - Slack channel name."
  type        = string
}

variable "display" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      message  = bool
      notified = bool
      snapshot = bool
      tags     = bool
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "datadog_integration_slack_channel" "this" {
  account_name = var.account_name
  channel_name = var.channel_name

  dynamic "display" {
    for_each = var.display
    content {
      message  = display.value["message"]
      notified = display.value["notified"]
      snapshot = display.value["snapshot"]
      tags     = display.value["tags"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_integration_slack_channel.this.id
}

output "this" {
  value = datadog_integration_slack_channel.this
}
```

[top](#index)