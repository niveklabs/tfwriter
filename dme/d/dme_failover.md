# dme_failover

[back](../dme.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dme = ">= 0.1.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dme_failover" {
  source = "./modules/dme/d/dme_failover"

  # auto_failover - (optional) is a type of string
  auto_failover = null
  # contact_list - (optional) is a type of string
  contact_list = null
  # dns_fqdn - (optional) is a type of string
  dns_fqdn = null
  # dns_timeout - (optional) is a type of string
  dns_timeout = null
  # failover - (optional) is a type of string
  failover = null
  # http_file - (optional) is a type of string
  http_file = null
  # http_fqdn - (optional) is a type of string
  http_fqdn = null
  # http_query_string - (optional) is a type of string
  http_query_string = null
  # ip1 - (optional) is a type of string
  ip1 = null
  # ip2 - (optional) is a type of string
  ip2 = null
  # ip3 - (optional) is a type of string
  ip3 = null
  # ip4 - (optional) is a type of string
  ip4 = null
  # ip5 - (optional) is a type of string
  ip5 = null
  # max_emails - (optional) is a type of string
  max_emails = null
  # monitor - (optional) is a type of string
  monitor = null
  # port - (optional) is a type of string
  port = null
  # protocol_id - (optional) is a type of string
  protocol_id = null
  # record_id - (required) is a type of string
  record_id = null
  # send_string - (optional) is a type of string
  send_string = null
  # sensitivity - (optional) is a type of string
  sensitivity = null
  # system_description - (optional) is a type of string
  system_description = null
  # timeout - (optional) is a type of string
  timeout = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_failover" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "contact_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_fqdn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_timeout" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "failover" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_fqdn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_query_string" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip3" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip4" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip5" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_emails" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "monitor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "record_id" {
  description = "(required)"
  type        = string
}

variable "send_string" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sensitivity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "system_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeout" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "dme_failover" "this" {
  # auto_failover - (optional) is a type of string
  auto_failover = var.auto_failover
  # contact_list - (optional) is a type of string
  contact_list = var.contact_list
  # dns_fqdn - (optional) is a type of string
  dns_fqdn = var.dns_fqdn
  # dns_timeout - (optional) is a type of string
  dns_timeout = var.dns_timeout
  # failover - (optional) is a type of string
  failover = var.failover
  # http_file - (optional) is a type of string
  http_file = var.http_file
  # http_fqdn - (optional) is a type of string
  http_fqdn = var.http_fqdn
  # http_query_string - (optional) is a type of string
  http_query_string = var.http_query_string
  # ip1 - (optional) is a type of string
  ip1 = var.ip1
  # ip2 - (optional) is a type of string
  ip2 = var.ip2
  # ip3 - (optional) is a type of string
  ip3 = var.ip3
  # ip4 - (optional) is a type of string
  ip4 = var.ip4
  # ip5 - (optional) is a type of string
  ip5 = var.ip5
  # max_emails - (optional) is a type of string
  max_emails = var.max_emails
  # monitor - (optional) is a type of string
  monitor = var.monitor
  # port - (optional) is a type of string
  port = var.port
  # protocol_id - (optional) is a type of string
  protocol_id = var.protocol_id
  # record_id - (required) is a type of string
  record_id = var.record_id
  # send_string - (optional) is a type of string
  send_string = var.send_string
  # sensitivity - (optional) is a type of string
  sensitivity = var.sensitivity
  # system_description - (optional) is a type of string
  system_description = var.system_description
  # timeout - (optional) is a type of string
  timeout = var.timeout
}
```

[top](#index)

### Outputs

```terraform
output "auto_failover" {
  description = "returns a string"
  value       = data.dme_failover.this.auto_failover
}

output "contact_list" {
  description = "returns a string"
  value       = data.dme_failover.this.contact_list
}

output "dns_fqdn" {
  description = "returns a string"
  value       = data.dme_failover.this.dns_fqdn
}

output "dns_timeout" {
  description = "returns a string"
  value       = data.dme_failover.this.dns_timeout
}

output "failover" {
  description = "returns a string"
  value       = data.dme_failover.this.failover
}

output "http_file" {
  description = "returns a string"
  value       = data.dme_failover.this.http_file
}

output "http_fqdn" {
  description = "returns a string"
  value       = data.dme_failover.this.http_fqdn
}

output "http_query_string" {
  description = "returns a string"
  value       = data.dme_failover.this.http_query_string
}

output "id" {
  description = "returns a string"
  value       = data.dme_failover.this.id
}

output "ip1" {
  description = "returns a string"
  value       = data.dme_failover.this.ip1
}

output "ip2" {
  description = "returns a string"
  value       = data.dme_failover.this.ip2
}

output "ip3" {
  description = "returns a string"
  value       = data.dme_failover.this.ip3
}

output "ip4" {
  description = "returns a string"
  value       = data.dme_failover.this.ip4
}

output "ip5" {
  description = "returns a string"
  value       = data.dme_failover.this.ip5
}

output "max_emails" {
  description = "returns a string"
  value       = data.dme_failover.this.max_emails
}

output "monitor" {
  description = "returns a string"
  value       = data.dme_failover.this.monitor
}

output "port" {
  description = "returns a string"
  value       = data.dme_failover.this.port
}

output "protocol_id" {
  description = "returns a string"
  value       = data.dme_failover.this.protocol_id
}

output "send_string" {
  description = "returns a string"
  value       = data.dme_failover.this.send_string
}

output "sensitivity" {
  description = "returns a string"
  value       = data.dme_failover.this.sensitivity
}

output "system_description" {
  description = "returns a string"
  value       = data.dme_failover.this.system_description
}

output "timeout" {
  description = "returns a string"
  value       = data.dme_failover.this.timeout
}

output "this" {
  value = dme_failover.this
}
```

[top](#index)