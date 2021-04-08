# turbot_control

[back](../turbot.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    turbot = ">= 1.8.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "turbot_control" {
  source = "./modules/turbot/d/turbot_control"

  # resource - (optional) is a type of string
  resource = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "resource" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "turbot_control" "this" {
  # resource - (optional) is a type of string
  resource = var.resource
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "details" {
  description = "returns a string"
  value       = data.turbot_control.this.details
}

output "id" {
  description = "returns a string"
  value       = data.turbot_control.this.id
}

output "reason" {
  description = "returns a string"
  value       = data.turbot_control.this.reason
}

output "state" {
  description = "returns a string"
  value       = data.turbot_control.this.state
}

output "this" {
  value = turbot_control.this
}
```

[top](#index)