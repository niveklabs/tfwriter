# akamai_networklist_activations

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
module "akamai_networklist_activations" {
  source = "./modules/akamai/r/akamai_networklist_activations"

  # activate - (optional) is a type of bool
  activate = null
  # network - (optional) is a type of string
  network = null
  # network_list_id - (required) is a type of string
  network_list_id = null
  # notes - (optional) is a type of string
  notes = null
  # notification_emails - (required) is a type of set of string
  notification_emails = []
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

variable "network" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_list_id" {
  description = "(required)"
  type        = string
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
```

[top](#index)

### Resource

```terraform
resource "akamai_networklist_activations" "this" {
  # activate - (optional) is a type of bool
  activate = var.activate
  # network - (optional) is a type of string
  network = var.network
  # network_list_id - (required) is a type of string
  network_list_id = var.network_list_id
  # notes - (optional) is a type of string
  notes = var.notes
  # notification_emails - (required) is a type of set of string
  notification_emails = var.notification_emails
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_networklist_activations.this.id
}

output "status" {
  description = "returns a string"
  value       = akamai_networklist_activations.this.status
}

output "this" {
  value = akamai_networklist_activations.this
}
```

[top](#index)