# newrelic_alert_channel

[back](../newrelic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    newrelic = ">= 2.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_alert_channel" {
  source = "./modules/newrelic/r/newrelic_alert_channel"

  # name - (required) is a type of string
  name = null
  # type - (required) is a type of string
  type = null

  config = [{
    api_key                 = null
    auth_password           = null
    auth_type               = null
    auth_username           = null
    base_url                = null
    channel                 = null
    headers                 = {}
    headers_string          = null
    include_json_attachment = null
    key                     = null
    payload                 = {}
    payload_string          = null
    payload_type            = null
    recipients              = null
    region                  = null
    route_key               = null
    service_key             = null
    tags                    = null
    teams                   = null
    url                     = null
    user_id                 = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - (Required) The name of the channel."
  type        = string
}

variable "type" {
  description = "(required) - (Required) The type of channel. One of: (email, opsgenie, pagerduty, slack, user, victorops, webhook)."
  type        = string
}

variable "config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      api_key                 = string
      auth_password           = string
      auth_type               = string
      auth_username           = string
      base_url                = string
      channel                 = string
      headers                 = map(string)
      headers_string          = string
      include_json_attachment = string
      key                     = string
      payload                 = map(string)
      payload_string          = string
      payload_type            = string
      recipients              = string
      region                  = string
      route_key               = string
      service_key             = string
      tags                    = string
      teams                   = string
      url                     = string
      user_id                 = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_alert_channel" "this" {
  # name - (required) is a type of string
  name = var.name
  # type - (required) is a type of string
  type = var.type

  dynamic "config" {
    for_each = var.config
    content {
      # api_key - (optional) is a type of string
      api_key = config.value["api_key"]
      # auth_password - (optional) is a type of string
      auth_password = config.value["auth_password"]
      # auth_type - (optional) is a type of string
      auth_type = config.value["auth_type"]
      # auth_username - (optional) is a type of string
      auth_username = config.value["auth_username"]
      # base_url - (optional) is a type of string
      base_url = config.value["base_url"]
      # channel - (optional) is a type of string
      channel = config.value["channel"]
      # headers - (optional) is a type of map of string
      headers = config.value["headers"]
      # headers_string - (optional) is a type of string
      headers_string = config.value["headers_string"]
      # include_json_attachment - (optional) is a type of string
      include_json_attachment = config.value["include_json_attachment"]
      # key - (optional) is a type of string
      key = config.value["key"]
      # payload - (optional) is a type of map of string
      payload = config.value["payload"]
      # payload_string - (optional) is a type of string
      payload_string = config.value["payload_string"]
      # payload_type - (optional) is a type of string
      payload_type = config.value["payload_type"]
      # recipients - (optional) is a type of string
      recipients = config.value["recipients"]
      # region - (optional) is a type of string
      region = config.value["region"]
      # route_key - (optional) is a type of string
      route_key = config.value["route_key"]
      # service_key - (optional) is a type of string
      service_key = config.value["service_key"]
      # tags - (optional) is a type of string
      tags = config.value["tags"]
      # teams - (optional) is a type of string
      teams = config.value["teams"]
      # url - (optional) is a type of string
      url = config.value["url"]
      # user_id - (optional) is a type of string
      user_id = config.value["user_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = newrelic_alert_channel.this.id
}

output "this" {
  value = newrelic_alert_channel.this
}
```

[top](#index)