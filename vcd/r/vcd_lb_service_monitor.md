# vcd_lb_service_monitor

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_lb_service_monitor" {
  source = "./modules/vcd/r/vcd_lb_service_monitor"

  # edge_gateway - (required) is a type of string
  edge_gateway = null
  # expected - (optional) is a type of string
  expected = null
  # extension - (optional) is a type of map of string
  extension = {}
  # interval - (optional) is a type of number
  interval = null
  # max_retries - (optional) is a type of number
  max_retries = null
  # method - (optional) is a type of string
  method = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # receive - (optional) is a type of string
  receive = null
  # send - (optional) is a type of string
  send = null
  # timeout - (optional) is a type of number
  timeout = null
  # type - (required) is a type of string
  type = null
  # url - (optional) is a type of string
  url = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "edge_gateway" {
  description = "(required) - Edge gateway name in which the LB Service Monitor is located"
  type        = string
}

variable "expected" {
  description = "(optional) - String that the monitor expects to match in the status line of the http or https response (for example, HTTP/1.1)"
  type        = string
  default     = null
}

variable "extension" {
  description = "(optional) - Advanced monitor parameters as key=value pairs"
  type        = map(string)
  default     = null
}

variable "interval" {
  description = "(optional) - Interval in seconds at which a server is to be monitored (defaults to 10)"
  type        = number
  default     = null
}

variable "max_retries" {
  description = "(optional) - Number of times the specified monitoring Method must fail sequentially before the server is declared down  (defaults to 3)"
  type        = number
  default     = null
}

variable "method" {
  description = "(optional) - Method to be used to detect server status. One of OPTIONS, GET, HEAD, POST, PUT, DELETE, TRACE, or CONNECT"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Unique LB Service Monitor name"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "receive" {
  description = "(optional) - String to be matched in the response content"
  type        = string
  default     = null
}

variable "send" {
  description = "(optional) - Data to be sent"
  type        = string
  default     = null
}

variable "timeout" {
  description = "(optional) - Maximum time in seconds within which a response from the server must be received  (defaults to 15)"
  type        = number
  default     = null
}

variable "type" {
  description = "(required) - Way in which you want to send the health check request to the server. One of http, https, tcp, icmp, or udp"
  type        = string
}

variable "url" {
  description = "(optional) - URL to be used in the server status request"
  type        = string
  default     = null
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vcd_lb_service_monitor" "this" {
  # edge_gateway - (required) is a type of string
  edge_gateway = var.edge_gateway
  # expected - (optional) is a type of string
  expected = var.expected
  # extension - (optional) is a type of map of string
  extension = var.extension
  # interval - (optional) is a type of number
  interval = var.interval
  # max_retries - (optional) is a type of number
  max_retries = var.max_retries
  # method - (optional) is a type of string
  method = var.method
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # receive - (optional) is a type of string
  receive = var.receive
  # send - (optional) is a type of string
  send = var.send
  # timeout - (optional) is a type of number
  timeout = var.timeout
  # type - (required) is a type of string
  type = var.type
  # url - (optional) is a type of string
  url = var.url
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_lb_service_monitor.this.id
}

output "this" {
  value = vcd_lb_service_monitor.this
}
```

[top](#index)