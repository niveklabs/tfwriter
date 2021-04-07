# tencentcloud_gaap_layer7_listener

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_gaap_layer7_listener" {
  source = "./modules/tencentcloud/r/tencentcloud_gaap_layer7_listener"

  # auth_type - (optional) is a type of number
  auth_type = null
  # certificate_id - (optional) is a type of string
  certificate_id = null
  # client_certificate_id - (optional) is a type of string
  client_certificate_id = null
  # client_certificate_ids - (optional) is a type of set of string
  client_certificate_ids = []
  # forward_protocol - (optional) is a type of string
  forward_protocol = null
  # name - (required) is a type of string
  name = null
  # port - (required) is a type of number
  port = null
  # protocol - (required) is a type of string
  protocol = null
  # proxy_id - (required) is a type of string
  proxy_id = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_type" {
  description = "(optional) - Authentication type of the layer7 listener. `0` is one-way authentication and `1` is mutual authentication. NOTES: Only supports listeners of `HTTPS` protocol."
  type        = number
  default     = null
}

variable "certificate_id" {
  description = "(optional) - Certificate ID of the layer7 listener. NOTES: Only supports listeners of `HTTPS` protocol."
  type        = string
  default     = null
}

variable "client_certificate_id" {
  description = "(optional) - ID of the client certificate. Set only when `auth_type` is specified as mutual authentication. NOTES: Only supports listeners of `HTTPS` protocol."
  type        = string
  default     = null
}

variable "client_certificate_ids" {
  description = "(optional) - ID list of the client certificate. Set only when `auth_type` is specified as mutual authentication. NOTES: Only supports listeners of `HTTPS` protocol."
  type        = set(string)
  default     = null
}

variable "forward_protocol" {
  description = "(optional) - Protocol type of the forwarding. Valid value: `HTTP` and `HTTPS`. NOTES: Only supports listeners of `HTTPS` protocol."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the layer7 listener, the maximum length is 30."
  type        = string
}

variable "port" {
  description = "(required) - Port of the layer7 listener."
  type        = number
}

variable "protocol" {
  description = "(required) - Protocol of the layer7 listener. Valid value: `HTTP` and `HTTPS`."
  type        = string
}

variable "proxy_id" {
  description = "(required) - ID of the GAAP proxy."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_gaap_layer7_listener" "this" {
  # auth_type - (optional) is a type of number
  auth_type = var.auth_type
  # certificate_id - (optional) is a type of string
  certificate_id = var.certificate_id
  # client_certificate_id - (optional) is a type of string
  client_certificate_id = var.client_certificate_id
  # client_certificate_ids - (optional) is a type of set of string
  client_certificate_ids = var.client_certificate_ids
  # forward_protocol - (optional) is a type of string
  forward_protocol = var.forward_protocol
  # name - (required) is a type of string
  name = var.name
  # port - (required) is a type of number
  port = var.port
  # protocol - (required) is a type of string
  protocol = var.protocol
  # proxy_id - (required) is a type of string
  proxy_id = var.proxy_id
}
```

[top](#index)

### Outputs

```terraform
output "client_certificate_id" {
  description = "returns a string"
  value       = tencentcloud_gaap_layer7_listener.this.client_certificate_id
}

output "client_certificate_ids" {
  description = "returns a set of string"
  value       = tencentcloud_gaap_layer7_listener.this.client_certificate_ids
}

output "create_time" {
  description = "returns a string"
  value       = tencentcloud_gaap_layer7_listener.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_gaap_layer7_listener.this.id
}

output "status" {
  description = "returns a number"
  value       = tencentcloud_gaap_layer7_listener.this.status
}

output "this" {
  value = tencentcloud_gaap_layer7_listener.this
}
```

[top](#index)