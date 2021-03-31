# alicloud_fc_function_async_invoke_config

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_fc_function_async_invoke_config" {
  source = "./modules/alicloud/r/alicloud_fc_function_async_invoke_config"

  # function_name - (required) is a type of string
  function_name = null
  # maximum_event_age_in_seconds - (optional) is a type of number
  maximum_event_age_in_seconds = null
  # maximum_retry_attempts - (optional) is a type of number
  maximum_retry_attempts = null
  # qualifier - (optional) is a type of string
  qualifier = null
  # service_name - (required) is a type of string
  service_name = null

  destination_config = [{
    on_failure = [{
      destination = null
    }]
    on_success = [{
      destination = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "function_name" {
  description = "(required)"
  type        = string
}

variable "maximum_event_age_in_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "maximum_retry_attempts" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "qualifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_name" {
  description = "(required)"
  type        = string
}

variable "destination_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      on_failure = list(object(
        {
          destination = string
        }
      ))
      on_success = list(object(
        {
          destination = string
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
resource "alicloud_fc_function_async_invoke_config" "this" {
  function_name                = var.function_name
  maximum_event_age_in_seconds = var.maximum_event_age_in_seconds
  maximum_retry_attempts       = var.maximum_retry_attempts
  qualifier                    = var.qualifier
  service_name                 = var.service_name

  dynamic "destination_config" {
    for_each = var.destination_config
    content {

      dynamic "on_failure" {
        for_each = destination_config.value.on_failure
        content {
          destination = on_failure.value["destination"]
        }
      }

      dynamic "on_success" {
        for_each = destination_config.value.on_success
        content {
          destination = on_success.value["destination"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_time" {
  description = "returns a string"
  value       = alicloud_fc_function_async_invoke_config.this.created_time
}

output "id" {
  description = "returns a string"
  value       = alicloud_fc_function_async_invoke_config.this.id
}

output "last_modified_time" {
  description = "returns a string"
  value       = alicloud_fc_function_async_invoke_config.this.last_modified_time
}

output "this" {
  value = alicloud_fc_function_async_invoke_config.this
}
```

[top](#index)