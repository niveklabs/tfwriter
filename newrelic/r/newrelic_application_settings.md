# newrelic_application_settings

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
module "newrelic_application_settings" {
  source = "./modules/newrelic/r/newrelic_application_settings"

  # app_apdex_threshold - (required) is a type of number
  app_apdex_threshold = null
  # enable_real_user_monitoring - (required) is a type of bool
  enable_real_user_monitoring = null
  # end_user_apdex_threshold - (required) is a type of number
  end_user_apdex_threshold = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "app_apdex_threshold" {
  description = "(required)"
  type        = number
}

variable "enable_real_user_monitoring" {
  description = "(required)"
  type        = bool
}

variable "end_user_apdex_threshold" {
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_application_settings" "this" {
  app_apdex_threshold         = var.app_apdex_threshold
  enable_real_user_monitoring = var.enable_real_user_monitoring
  end_user_apdex_threshold    = var.end_user_apdex_threshold
  name                        = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = newrelic_application_settings.this.id
}

output "this" {
  value = newrelic_application_settings.this
}
```

[top](#index)