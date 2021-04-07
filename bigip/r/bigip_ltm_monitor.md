# bigip_ltm_monitor

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_monitor" {
  source = "./modules/bigip/r/bigip_ltm_monitor"

  # adaptive - (optional) is a type of string
  adaptive = null
  # adaptive_limit - (optional) is a type of number
  adaptive_limit = null
  # compatibility - (optional) is a type of string
  compatibility = null
  # database - (optional) is a type of string
  database = null
  # defaults_from - (optional) is a type of string
  defaults_from = null
  # destination - (optional) is a type of string
  destination = null
  # filename - (optional) is a type of string
  filename = null
  # interval - (optional) is a type of number
  interval = null
  # ip_dscp - (optional) is a type of number
  ip_dscp = null
  # manual_resume - (optional) is a type of string
  manual_resume = null
  # mode - (optional) is a type of string
  mode = null
  # name - (required) is a type of string
  name = null
  # parent - (required) is a type of string
  parent = null
  # password - (optional) is a type of string
  password = null
  # receive - (optional) is a type of string
  receive = null
  # receive_disable - (optional) is a type of string
  receive_disable = null
  # reverse - (optional) is a type of string
  reverse = null
  # send - (optional) is a type of string
  send = null
  # time_until_up - (optional) is a type of number
  time_until_up = null
  # timeout - (optional) is a type of number
  timeout = null
  # transparent - (optional) is a type of string
  transparent = null
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "adaptive" {
  description = "(optional) - ftp adaptive"
  type        = string
  default     = null
}

variable "adaptive_limit" {
  description = "(optional) - Integer value"
  type        = number
  default     = null
}

variable "compatibility" {
  description = "(optional) - Specifies, when enabled, that the SSL options setting (in OpenSSL) is set to ALL. The default value is enabled."
  type        = string
  default     = null
}

variable "database" {
  description = "(optional) - the database in which your user is created"
  type        = string
  default     = null
}

variable "defaults_from" {
  description = "(optional) - Existing monitor to inherit from. Must be one of /Common/http, /Common/https, /Common/icmp or /Common/gateway-icmp."
  type        = string
  default     = null
}

variable "destination" {
  description = "(optional) - Alias for the destination"
  type        = string
  default     = null
}

variable "filename" {
  description = "(optional) - Specifies the full path and file name of the file that the system attempts to download. The health check is successful if the system can download the file."
  type        = string
  default     = null
}

variable "interval" {
  description = "(optional) - Check interval in seconds"
  type        = number
  default     = null
}

variable "ip_dscp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "manual_resume" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional) - Specifies the data transfer process (DTP) mode. The default value is passive."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the monitor"
  type        = string
}

variable "parent" {
  description = "(required) - Existing monitor to inherit from. Must be one of /Common/http, /Common/https, /Common/icmp or /Common/gateway-icmp."
  type        = string
}

variable "password" {
  description = "(optional) - Specifies the password if the monitored target requires authentication"
  type        = string
  default     = null
}

variable "receive" {
  description = "(optional) - Expected response string."
  type        = string
  default     = null
}

variable "receive_disable" {
  description = "(optional) - Expected response string."
  type        = string
  default     = null
}

variable "reverse" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "send" {
  description = "(optional) - Request string to send."
  type        = string
  default     = null
}

variable "time_until_up" {
  description = "(optional) - Time in seconds"
  type        = number
  default     = null
}

variable "timeout" {
  description = "(optional) - Timeout in seconds"
  type        = number
  default     = null
}

variable "transparent" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional) - Specifies the user name if the monitored target requires authentication"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_monitor" "this" {
  # adaptive - (optional) is a type of string
  adaptive = var.adaptive
  # adaptive_limit - (optional) is a type of number
  adaptive_limit = var.adaptive_limit
  # compatibility - (optional) is a type of string
  compatibility = var.compatibility
  # database - (optional) is a type of string
  database = var.database
  # defaults_from - (optional) is a type of string
  defaults_from = var.defaults_from
  # destination - (optional) is a type of string
  destination = var.destination
  # filename - (optional) is a type of string
  filename = var.filename
  # interval - (optional) is a type of number
  interval = var.interval
  # ip_dscp - (optional) is a type of number
  ip_dscp = var.ip_dscp
  # manual_resume - (optional) is a type of string
  manual_resume = var.manual_resume
  # mode - (optional) is a type of string
  mode = var.mode
  # name - (required) is a type of string
  name = var.name
  # parent - (required) is a type of string
  parent = var.parent
  # password - (optional) is a type of string
  password = var.password
  # receive - (optional) is a type of string
  receive = var.receive
  # receive_disable - (optional) is a type of string
  receive_disable = var.receive_disable
  # reverse - (optional) is a type of string
  reverse = var.reverse
  # send - (optional) is a type of string
  send = var.send
  # time_until_up - (optional) is a type of number
  time_until_up = var.time_until_up
  # timeout - (optional) is a type of number
  timeout = var.timeout
  # transparent - (optional) is a type of string
  transparent = var.transparent
  # username - (optional) is a type of string
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "adaptive" {
  description = "returns a string"
  value       = bigip_ltm_monitor.this.adaptive
}

output "adaptive_limit" {
  description = "returns a number"
  value       = bigip_ltm_monitor.this.adaptive_limit
}

output "destination" {
  description = "returns a string"
  value       = bigip_ltm_monitor.this.destination
}

output "id" {
  description = "returns a string"
  value       = bigip_ltm_monitor.this.id
}

output "interval" {
  description = "returns a number"
  value       = bigip_ltm_monitor.this.interval
}

output "ip_dscp" {
  description = "returns a number"
  value       = bigip_ltm_monitor.this.ip_dscp
}

output "manual_resume" {
  description = "returns a string"
  value       = bigip_ltm_monitor.this.manual_resume
}

output "mode" {
  description = "returns a string"
  value       = bigip_ltm_monitor.this.mode
}

output "reverse" {
  description = "returns a string"
  value       = bigip_ltm_monitor.this.reverse
}

output "send" {
  description = "returns a string"
  value       = bigip_ltm_monitor.this.send
}

output "time_until_up" {
  description = "returns a number"
  value       = bigip_ltm_monitor.this.time_until_up
}

output "timeout" {
  description = "returns a number"
  value       = bigip_ltm_monitor.this.timeout
}

output "transparent" {
  description = "returns a string"
  value       = bigip_ltm_monitor.this.transparent
}

output "this" {
  value = bigip_ltm_monitor.this
}
```

[top](#index)