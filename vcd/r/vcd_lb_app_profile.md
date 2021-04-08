# vcd_lb_app_profile

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
module "vcd_lb_app_profile" {
  source = "./modules/vcd/r/vcd_lb_app_profile"

  # cookie_mode - (optional) is a type of string
  cookie_mode = null
  # cookie_name - (optional) is a type of string
  cookie_name = null
  # edge_gateway - (required) is a type of string
  edge_gateway = null
  # enable_pool_side_ssl - (optional) is a type of bool
  enable_pool_side_ssl = null
  # enable_ssl_passthrough - (optional) is a type of bool
  enable_ssl_passthrough = null
  # expiration - (optional) is a type of number
  expiration = null
  # http_redirect_url - (optional) is a type of string
  http_redirect_url = null
  # insert_x_forwarded_http_header - (optional) is a type of bool
  insert_x_forwarded_http_header = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # persistence_mechanism - (optional) is a type of string
  persistence_mechanism = null
  # type - (required) is a type of string
  type = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "cookie_mode" {
  description = "(optional) - The mode by which the cookie should be inserted. One of 'insert', 'prefix', or 'appsession'"
  type        = string
  default     = null
}

variable "cookie_name" {
  description = "(optional) - Used to uniquely identify the session the first time a client accesses the site. The load balancer refers to this cookie when connecting subsequent requests in the session, so that they all go to the same virtual server. Only applies for persistence_mechanism 'cookie'"
  type        = string
  default     = null
}

variable "edge_gateway" {
  description = "(required) - Edge gateway name in which the LB Application Profile is located"
  type        = string
}

variable "enable_pool_side_ssl" {
  description = "(optional) - Enable to define the certificate, CAs, or CRLs used to authenticate the load balancer from the server side"
  type        = bool
  default     = null
}

variable "enable_ssl_passthrough" {
  description = "(optional) - Enable SSL authentication to be passed through to the virtual server. Otherwise SSL authentication takes place at the destination address."
  type        = bool
  default     = null
}

variable "expiration" {
  description = "(optional) - Length of time in seconds that persistence stays in effect"
  type        = number
  default     = null
}

variable "http_redirect_url" {
  description = "(optional) - The URL to which traffic that arrives at the destination address should be redirected. Only applies for types 'http' and 'https'"
  type        = string
  default     = null
}

variable "insert_x_forwarded_http_header" {
  description = "(optional) - Enables 'X-Forwarded-For' header for identifying the originating IP address of a client connecting to a Web server through the load balancer. Only applies for types HTTP and HTTPS"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Unique LB Application Profile name"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "persistence_mechanism" {
  description = "(optional) - Persistence mechanism for the profile. One of 'cookie', 'ssl-sessionid', 'sourceip'"
  type        = string
  default     = null
}

variable "type" {
  description = "(required) - Protocol type used to send requests to the server. One of 'tcp', 'udp', 'http' org 'https'"
  type        = string
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
resource "vcd_lb_app_profile" "this" {
  # cookie_mode - (optional) is a type of string
  cookie_mode = var.cookie_mode
  # cookie_name - (optional) is a type of string
  cookie_name = var.cookie_name
  # edge_gateway - (required) is a type of string
  edge_gateway = var.edge_gateway
  # enable_pool_side_ssl - (optional) is a type of bool
  enable_pool_side_ssl = var.enable_pool_side_ssl
  # enable_ssl_passthrough - (optional) is a type of bool
  enable_ssl_passthrough = var.enable_ssl_passthrough
  # expiration - (optional) is a type of number
  expiration = var.expiration
  # http_redirect_url - (optional) is a type of string
  http_redirect_url = var.http_redirect_url
  # insert_x_forwarded_http_header - (optional) is a type of bool
  insert_x_forwarded_http_header = var.insert_x_forwarded_http_header
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # persistence_mechanism - (optional) is a type of string
  persistence_mechanism = var.persistence_mechanism
  # type - (required) is a type of string
  type = var.type
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_lb_app_profile.this.id
}

output "this" {
  value = vcd_lb_app_profile.this
}
```

[top](#index)