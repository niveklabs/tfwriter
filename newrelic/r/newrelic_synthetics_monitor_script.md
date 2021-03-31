# newrelic_synthetics_monitor_script

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
module "newrelic_synthetics_monitor_script" {
  source = "./modules/newrelic/r/newrelic_synthetics_monitor_script"

  # monitor_id - (required) is a type of string
  monitor_id = null
  # text - (required) is a type of string
  text = null
}
```

[top](#index)

### Variables

```terraform
variable "monitor_id" {
  description = "(required) - The ID of the monitor to attach the script to."
  type        = string
}

variable "text" {
  description = "(required) - The plaintext representing the monitor script."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_synthetics_monitor_script" "this" {
  monitor_id = var.monitor_id
  text       = var.text
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = newrelic_synthetics_monitor_script.this.id
}

output "this" {
  value = newrelic_synthetics_monitor_script.this
}
```

[top](#index)