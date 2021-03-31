# linode_nodebalancer_config

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.16.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_nodebalancer_config" {
  source = "./modules/linode/r/linode_nodebalancer_config"

  # algorithm - (optional) is a type of string
  algorithm = null
  # check - (optional) is a type of string
  check = null
  # check_attempts - (optional) is a type of number
  check_attempts = null
  # check_body - (optional) is a type of string
  check_body = null
  # check_interval - (optional) is a type of number
  check_interval = null
  # check_passive - (optional) is a type of bool
  check_passive = null
  # check_path - (optional) is a type of string
  check_path = null
  # check_timeout - (optional) is a type of number
  check_timeout = null
  # cipher_suite - (optional) is a type of string
  cipher_suite = null
  # nodebalancer_id - (required) is a type of number
  nodebalancer_id = null
  # port - (optional) is a type of number
  port = null
  # protocol - (optional) is a type of string
  protocol = null
  # proxy_protocol - (optional) is a type of string
  proxy_protocol = null
  # ssl_cert - (optional) is a type of string
  ssl_cert = null
  # ssl_key - (optional) is a type of string
  ssl_key = null
  # stickiness - (optional) is a type of string
  stickiness = null
}
```

[top](#index)

### Variables

```terraform
variable "algorithm" {
  description = "(optional) - What algorithm this NodeBalancer should use for routing traffic to backends: roundrobin, leastconn, source"
  type        = string
  default     = null
}

variable "check" {
  description = "(optional) - The type of check to perform against backends to ensure they are serving requests. This is used to determine if backends are up or down. If none no check is performed. connection requires only a connection to the backend to succeed. http and http_body rely on the backend serving HTTP, and that the response returned matches what is expected."
  type        = string
  default     = null
}

variable "check_attempts" {
  description = "(optional) - How many times to attempt a check before considering a backend to be down. (1-30)"
  type        = number
  default     = null
}

variable "check_body" {
  description = "(optional) - This value must be present in the response body of the check in order for it to pass. If this value is not present in the response body of a check request, the backend is considered to be down"
  type        = string
  default     = null
}

variable "check_interval" {
  description = "(optional) - How often, in seconds, to check that backends are up and serving requests."
  type        = number
  default     = null
}

variable "check_passive" {
  description = "(optional) - If true, any response from this backend with a 5xx status code will be enough for it to be considered unhealthy and taken out of rotation."
  type        = bool
  default     = null
}

variable "check_path" {
  description = "(optional) - The URL path to check on each backend. If the backend does not respond to this request it is considered to be down."
  type        = string
  default     = null
}

variable "check_timeout" {
  description = "(optional) - How long, in seconds, to wait for a check attempt before considering it failed. (1-30)"
  type        = number
  default     = null
}

variable "cipher_suite" {
  description = "(optional) - What ciphers to use for SSL connections served by this NodeBalancer. `legacy` is considered insecure and should only be used if necessary."
  type        = string
  default     = null
}

variable "nodebalancer_id" {
  description = "(required) - The ID of the NodeBalancer to access."
  type        = number
}

variable "port" {
  description = "(optional) - The TCP port this Config is for. These values must be unique across configs on a single NodeBalancer (you can't have two configs for port 80, for example). While some ports imply some protocols, no enforcement is done and you may configure your NodeBalancer however is useful to you. For example, while port 443 is generally used for HTTPS, you do not need SSL configured to have a NodeBalancer listening on port 443."
  type        = number
  default     = null
}

variable "protocol" {
  description = "(optional) - The protocol this port is configured to serve. If this is set to https you must include an ssl_cert and an ssl_key."
  type        = string
  default     = null
}

variable "proxy_protocol" {
  description = "(optional) - The version of ProxyProtocol to use for the underlying NodeBalancer. This requires protocol to be `tcp`. Valid values are `none`, `v1`, and `v2`."
  type        = string
  default     = null
}

variable "ssl_cert" {
  description = "(optional) - The certificate this port is serving. This is not returned. If set, this field will come back as `<REDACTED>`. Please use the ssl_commonname and ssl_fingerprint to identify the certificate."
  type        = string
  default     = null
}

variable "ssl_key" {
  description = "(optional) - The private key corresponding to this port's certificate. This is not returned. If set, this field will come back as `<REDACTED>`. Please use the ssl_commonname and ssl_fingerprint to identify the certificate."
  type        = string
  default     = null
}

variable "stickiness" {
  description = "(optional) - Controls how session stickiness is handled on this port: 'none', 'table', 'http_cookie'"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "linode_nodebalancer_config" "this" {
  algorithm       = var.algorithm
  check           = var.check
  check_attempts  = var.check_attempts
  check_body      = var.check_body
  check_interval  = var.check_interval
  check_passive   = var.check_passive
  check_path      = var.check_path
  check_timeout   = var.check_timeout
  cipher_suite    = var.cipher_suite
  nodebalancer_id = var.nodebalancer_id
  port            = var.port
  protocol        = var.protocol
  proxy_protocol  = var.proxy_protocol
  ssl_cert        = var.ssl_cert
  ssl_key         = var.ssl_key
  stickiness      = var.stickiness
}
```

[top](#index)

### Outputs

```terraform
output "algorithm" {
  description = "returns a string"
  value       = linode_nodebalancer_config.this.algorithm
}

output "check" {
  description = "returns a string"
  value       = linode_nodebalancer_config.this.check
}

output "check_attempts" {
  description = "returns a number"
  value       = linode_nodebalancer_config.this.check_attempts
}

output "check_body" {
  description = "returns a string"
  value       = linode_nodebalancer_config.this.check_body
}

output "check_interval" {
  description = "returns a number"
  value       = linode_nodebalancer_config.this.check_interval
}

output "check_passive" {
  description = "returns a bool"
  value       = linode_nodebalancer_config.this.check_passive
}

output "check_path" {
  description = "returns a string"
  value       = linode_nodebalancer_config.this.check_path
}

output "check_timeout" {
  description = "returns a number"
  value       = linode_nodebalancer_config.this.check_timeout
}

output "cipher_suite" {
  description = "returns a string"
  value       = linode_nodebalancer_config.this.cipher_suite
}

output "id" {
  description = "returns a string"
  value       = linode_nodebalancer_config.this.id
}

output "node_status" {
  description = "returns a list of object"
  value       = linode_nodebalancer_config.this.node_status
}

output "ssl_commonname" {
  description = "returns a string"
  value       = linode_nodebalancer_config.this.ssl_commonname
}

output "ssl_fingerprint" {
  description = "returns a string"
  value       = linode_nodebalancer_config.this.ssl_fingerprint
}

output "stickiness" {
  description = "returns a string"
  value       = linode_nodebalancer_config.this.stickiness
}

output "this" {
  value = linode_nodebalancer_config.this
}
```

[top](#index)