# akamai_appsec_activations

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_appsec_activations" {
  source = "./modules/akamai/r/akamai_appsec_activations"

  # activate - (optional) is a type of bool
  activate = null
  # config_id - (required) is a type of number
  config_id = null
  # network - (optional) is a type of string
  network = null
  # notes - (optional) is a type of string
  notes = null
  # notification_emails - (required) is a type of set of string
  notification_emails = []
  # version - (required) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "activate" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "config_id" {
  description = "(required)"
  type        = number
}

variable "network" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "notes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "notification_emails" {
  description = "(required)"
  type        = set(string)
}

variable "version" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "akamai_appsec_activations" "this" {
  activate            = var.activate
  config_id           = var.config_id
  network             = var.network
  notes               = var.notes
  notification_emails = var.notification_emails
  version             = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_activations.this.id
}

output "status" {
  description = "returns a string"
  value       = akamai_appsec_activations.this.status
}

output "this" {
  value = akamai_appsec_activations.this
}
```

[top](#index)