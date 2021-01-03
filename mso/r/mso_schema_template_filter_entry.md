# mso_schema_template_filter_entry

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mso = ">= 0.1.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_schema_template_filter_entry" {
  source = "./modules/mso/r/mso_schema_template_filter_entry"

  # arp_flag - (optional) is a type of string
  arp_flag = null
  # destination_from - (optional) is a type of string
  destination_from = null
  # destination_to - (optional) is a type of string
  destination_to = null
  # display_name - (required) is a type of string
  display_name = null
  # entry_description - (optional) is a type of string
  entry_description = null
  # entry_display_name - (required) is a type of string
  entry_display_name = null
  # entry_name - (required) is a type of string
  entry_name = null
  # ether_type - (optional) is a type of string
  ether_type = null
  # ip_protocol - (optional) is a type of string
  ip_protocol = null
  # match_only_fragments - (optional) is a type of bool
  match_only_fragments = null
  # name - (required) is a type of string
  name = null
  # schema_id - (required) is a type of string
  schema_id = null
  # source_from - (optional) is a type of string
  source_from = null
  # source_to - (optional) is a type of string
  source_to = null
  # stateful - (optional) is a type of bool
  stateful = null
  # tcp_session_rules - (optional) is a type of list of string
  tcp_session_rules = []
  # template_name - (required) is a type of string
  template_name = null
}
```

[top](#index)

### Variables

```terraform
variable "arp_flag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_from" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_to" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "entry_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "entry_display_name" {
  description = "(required)"
  type        = string
}

variable "entry_name" {
  description = "(required)"
  type        = string
}

variable "ether_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "match_only_fragments" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "source_from" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_to" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stateful" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tcp_session_rules" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "template_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "mso_schema_template_filter_entry" "this" {
  arp_flag             = var.arp_flag
  destination_from     = var.destination_from
  destination_to       = var.destination_to
  display_name         = var.display_name
  entry_description    = var.entry_description
  entry_display_name   = var.entry_display_name
  entry_name           = var.entry_name
  ether_type           = var.ether_type
  ip_protocol          = var.ip_protocol
  match_only_fragments = var.match_only_fragments
  name                 = var.name
  schema_id            = var.schema_id
  source_from          = var.source_from
  source_to            = var.source_to
  stateful             = var.stateful
  tcp_session_rules    = var.tcp_session_rules
  template_name        = var.template_name
}
```

[top](#index)

### Outputs

```terraform
output "arp_flag" {
  description = "returns a string"
  value       = mso_schema_template_filter_entry.this.arp_flag
}

output "destination_from" {
  description = "returns a string"
  value       = mso_schema_template_filter_entry.this.destination_from
}

output "destination_to" {
  description = "returns a string"
  value       = mso_schema_template_filter_entry.this.destination_to
}

output "entry_description" {
  description = "returns a string"
  value       = mso_schema_template_filter_entry.this.entry_description
}

output "ether_type" {
  description = "returns a string"
  value       = mso_schema_template_filter_entry.this.ether_type
}

output "id" {
  description = "returns a string"
  value       = mso_schema_template_filter_entry.this.id
}

output "ip_protocol" {
  description = "returns a string"
  value       = mso_schema_template_filter_entry.this.ip_protocol
}

output "match_only_fragments" {
  description = "returns a bool"
  value       = mso_schema_template_filter_entry.this.match_only_fragments
}

output "source_from" {
  description = "returns a string"
  value       = mso_schema_template_filter_entry.this.source_from
}

output "source_to" {
  description = "returns a string"
  value       = mso_schema_template_filter_entry.this.source_to
}

output "stateful" {
  description = "returns a bool"
  value       = mso_schema_template_filter_entry.this.stateful
}

output "tcp_session_rules" {
  description = "returns a list of string"
  value       = mso_schema_template_filter_entry.this.tcp_session_rules
}

output "this" {
  value = mso_schema_template_filter_entry.this
}
```

[top](#index)