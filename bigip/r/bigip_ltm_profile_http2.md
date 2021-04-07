# bigip_ltm_profile_http2

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
module "bigip_ltm_profile_http2" {
  source = "./modules/bigip/r/bigip_ltm_profile_http2"

  # activation_modes - (optional) is a type of set of string
  activation_modes = []
  # concurrent_streams_per_connection - (optional) is a type of number
  concurrent_streams_per_connection = null
  # connection_idle_timeout - (optional) is a type of number
  connection_idle_timeout = null
  # defaults_from - (optional) is a type of string
  defaults_from = null
  # enforce_tls_requirements - (optional) is a type of string
  enforce_tls_requirements = null
  # frame_size - (optional) is a type of number
  frame_size = null
  # header_table_size - (optional) is a type of number
  header_table_size = null
  # include_content_length - (optional) is a type of string
  include_content_length = null
  # insert_header - (optional) is a type of string
  insert_header = null
  # insert_header_name - (optional) is a type of string
  insert_header_name = null
  # name - (required) is a type of string
  name = null
  # receive_window - (optional) is a type of number
  receive_window = null
  # write_size - (optional) is a type of number
  write_size = null
}
```

[top](#index)

### Variables

```terraform
variable "activation_modes" {
  description = "(optional) - This setting specifies the condition that will cause the BIG-IP system to handle an incoming connection as an HTTP/2 connection."
  type        = set(string)
  default     = null
}

variable "concurrent_streams_per_connection" {
  description = "(optional) - The number of concurrent connections to allow on a single HTTP/2 connection.Default is 10"
  type        = number
  default     = null
}

variable "connection_idle_timeout" {
  description = "(optional) - The number of seconds that a HTTP/2 connection is left open idly before it is closed"
  type        = number
  default     = null
}

variable "defaults_from" {
  description = "(optional) - Use the parent Http2 profile"
  type        = string
  default     = null
}

variable "enforce_tls_requirements" {
  description = "(optional) - Enable or disable enforcement of TLS requirements,Default:enabled"
  type        = string
  default     = null
}

variable "frame_size" {
  description = "(optional) - The size of the data frames, in bytes, that the HTTP/2 protocol sends to the client. Default: 2048"
  type        = number
  default     = null
}

variable "header_table_size" {
  description = "(optional) - The size of the header table, in KB, for the HTTP headers that the HTTP/2 protocol compresses to save bandwidth.Default: 4096"
  type        = number
  default     = null
}

variable "include_content_length" {
  description = "(optional) - Enable to include content-length in HTTP/2 headers,Default : disabled"
  type        = string
  default     = null
}

variable "insert_header" {
  description = "(optional) - This setting specifies whether the BIG-IP system should add an HTTP header to the HTTP request to show that the request was received over HTTP/2,Default:disabled"
  type        = string
  default     = null
}

variable "insert_header_name" {
  description = "(optional) - This setting specifies the name of the header that the BIG-IP system will add to the HTTP request when the Insert Header is enabled."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the Http2 Profile"
  type        = string
}

variable "receive_window" {
  description = "(optional) - The flow-control size for upload streams, in KB. Default: 32"
  type        = number
  default     = null
}

variable "write_size" {
  description = "(optional) - The total size of combined data frames, in bytes, that the HTTP/2 protocol sends in a single write function. Default: 16384"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_profile_http2" "this" {
  # activation_modes - (optional) is a type of set of string
  activation_modes = var.activation_modes
  # concurrent_streams_per_connection - (optional) is a type of number
  concurrent_streams_per_connection = var.concurrent_streams_per_connection
  # connection_idle_timeout - (optional) is a type of number
  connection_idle_timeout = var.connection_idle_timeout
  # defaults_from - (optional) is a type of string
  defaults_from = var.defaults_from
  # enforce_tls_requirements - (optional) is a type of string
  enforce_tls_requirements = var.enforce_tls_requirements
  # frame_size - (optional) is a type of number
  frame_size = var.frame_size
  # header_table_size - (optional) is a type of number
  header_table_size = var.header_table_size
  # include_content_length - (optional) is a type of string
  include_content_length = var.include_content_length
  # insert_header - (optional) is a type of string
  insert_header = var.insert_header
  # insert_header_name - (optional) is a type of string
  insert_header_name = var.insert_header_name
  # name - (required) is a type of string
  name = var.name
  # receive_window - (optional) is a type of number
  receive_window = var.receive_window
  # write_size - (optional) is a type of number
  write_size = var.write_size
}
```

[top](#index)

### Outputs

```terraform
output "activation_modes" {
  description = "returns a set of string"
  value       = bigip_ltm_profile_http2.this.activation_modes
}

output "concurrent_streams_per_connection" {
  description = "returns a number"
  value       = bigip_ltm_profile_http2.this.concurrent_streams_per_connection
}

output "connection_idle_timeout" {
  description = "returns a number"
  value       = bigip_ltm_profile_http2.this.connection_idle_timeout
}

output "defaults_from" {
  description = "returns a string"
  value       = bigip_ltm_profile_http2.this.defaults_from
}

output "enforce_tls_requirements" {
  description = "returns a string"
  value       = bigip_ltm_profile_http2.this.enforce_tls_requirements
}

output "frame_size" {
  description = "returns a number"
  value       = bigip_ltm_profile_http2.this.frame_size
}

output "header_table_size" {
  description = "returns a number"
  value       = bigip_ltm_profile_http2.this.header_table_size
}

output "id" {
  description = "returns a string"
  value       = bigip_ltm_profile_http2.this.id
}

output "include_content_length" {
  description = "returns a string"
  value       = bigip_ltm_profile_http2.this.include_content_length
}

output "insert_header" {
  description = "returns a string"
  value       = bigip_ltm_profile_http2.this.insert_header
}

output "insert_header_name" {
  description = "returns a string"
  value       = bigip_ltm_profile_http2.this.insert_header_name
}

output "receive_window" {
  description = "returns a number"
  value       = bigip_ltm_profile_http2.this.receive_window
}

output "write_size" {
  description = "returns a number"
  value       = bigip_ltm_profile_http2.this.write_size
}

output "this" {
  value = bigip_ltm_profile_http2.this
}
```

[top](#index)