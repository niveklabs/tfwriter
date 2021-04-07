# signalfx_data_link

[back](../signalfx.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    signalfx = ">= 6.7.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "signalfx_data_link" {
  source = "./modules/signalfx/r/signalfx_data_link"

  # context_dashboard_id - (optional) is a type of string
  context_dashboard_id = null
  # property_name - (optional) is a type of string
  property_name = null
  # property_value - (optional) is a type of string
  property_value = null

  target_external_url = [{
    minimum_time_window  = null
    name                 = null
    property_key_mapping = {}
    time_format          = null
    url                  = null
  }]

  target_signalfx_dashboard = [{
    dashboard_group_id = null
    dashboard_id       = null
    is_default         = null
    name               = null
  }]

  target_splunk = [{
    name                 = null
    property_key_mapping = {}
  }]
}
```

[top](#index)

### Variables

```terraform
variable "context_dashboard_id" {
  description = "(optional) - The dashobard ID to which this data link will be applied"
  type        = string
  default     = null
}

variable "property_name" {
  description = "(optional) - Name (key) of the metadata that's the trigger of a data link. If you specify `property_value`, you must specify `property_name`."
  type        = string
  default     = null
}

variable "property_value" {
  description = "(optional) - Value of the metadata that's the trigger of a data link. If you specify this property, you must also specify `property_name`."
  type        = string
  default     = null
}

variable "target_external_url" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      minimum_time_window  = string
      name                 = string
      property_key_mapping = map(string)
      time_format          = string
      url                  = string
    }
  ))
  default = []
}

variable "target_signalfx_dashboard" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      dashboard_group_id = string
      dashboard_id       = string
      is_default         = bool
      name               = string
    }
  ))
  default = []
}

variable "target_splunk" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name                 = string
      property_key_mapping = map(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "signalfx_data_link" "this" {
  # context_dashboard_id - (optional) is a type of string
  context_dashboard_id = var.context_dashboard_id
  # property_name - (optional) is a type of string
  property_name = var.property_name
  # property_value - (optional) is a type of string
  property_value = var.property_value

  dynamic "target_external_url" {
    for_each = var.target_external_url
    content {
      # minimum_time_window - (optional) is a type of string
      minimum_time_window = target_external_url.value["minimum_time_window"]
      # name - (required) is a type of string
      name = target_external_url.value["name"]
      # property_key_mapping - (optional) is a type of map of string
      property_key_mapping = target_external_url.value["property_key_mapping"]
      # time_format - (optional) is a type of string
      time_format = target_external_url.value["time_format"]
      # url - (required) is a type of string
      url = target_external_url.value["url"]
    }
  }

  dynamic "target_signalfx_dashboard" {
    for_each = var.target_signalfx_dashboard
    content {
      # dashboard_group_id - (required) is a type of string
      dashboard_group_id = target_signalfx_dashboard.value["dashboard_group_id"]
      # dashboard_id - (required) is a type of string
      dashboard_id = target_signalfx_dashboard.value["dashboard_id"]
      # is_default - (optional) is a type of bool
      is_default = target_signalfx_dashboard.value["is_default"]
      # name - (required) is a type of string
      name = target_signalfx_dashboard.value["name"]
    }
  }

  dynamic "target_splunk" {
    for_each = var.target_splunk
    content {
      # name - (required) is a type of string
      name = target_splunk.value["name"]
      # property_key_mapping - (optional) is a type of map of string
      property_key_mapping = target_splunk.value["property_key_mapping"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = signalfx_data_link.this.id
}

output "this" {
  value = signalfx_data_link.this
}
```

[top](#index)