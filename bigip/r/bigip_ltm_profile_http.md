# bigip_ltm_profile_http

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
module "bigip_ltm_profile_http" {
  source = "./modules/bigip/r/bigip_ltm_profile_http"

  # accept_xff - (optional) is a type of string
  accept_xff = null
  # app_service - (optional) is a type of string
  app_service = null
  # basic_auth_realm - (optional) is a type of string
  basic_auth_realm = null
  # defaults_from - (optional) is a type of string
  defaults_from = null
  # description - (optional) is a type of string
  description = null
  # encrypt_cookie_secret - (optional) is a type of string
  encrypt_cookie_secret = null
  # encrypt_cookies - (optional) is a type of set of string
  encrypt_cookies = []
  # fallback_host - (optional) is a type of string
  fallback_host = null
  # fallback_status_codes - (optional) is a type of set of string
  fallback_status_codes = []
  # head_erase - (optional) is a type of string
  head_erase = null
  # head_insert - (optional) is a type of string
  head_insert = null
  # insert_xforwarded_for - (optional) is a type of string
  insert_xforwarded_for = null
  # lws_separator - (optional) is a type of string
  lws_separator = null
  # name - (required) is a type of string
  name = null
  # oneconnect_transformations - (optional) is a type of string
  oneconnect_transformations = null
  # proxy_type - (optional) is a type of string
  proxy_type = null
  # redirect_rewrite - (optional) is a type of string
  redirect_rewrite = null
  # request_chunking - (optional) is a type of string
  request_chunking = null
  # response_chunking - (optional) is a type of string
  response_chunking = null
  # response_headers_permitted - (optional) is a type of set of string
  response_headers_permitted = []
  # server_agent_name - (optional) is a type of string
  server_agent_name = null
  # tm_partition - (optional) is a type of string
  tm_partition = null
  # via_host_name - (optional) is a type of string
  via_host_name = null
  # via_request - (optional) is a type of string
  via_request = null
  # via_response - (optional) is a type of string
  via_response = null
  # xff_alternative_names - (optional) is a type of set of string
  xff_alternative_names = []
}
```

[top](#index)

### Variables

```terraform
variable "accept_xff" {
  description = "(optional) - Enables or disables trusting the client IP address, and statistics from the client IP address, based on the request's XFF (X-forwarded-for) headers, if they exist."
  type        = string
  default     = null
}

variable "app_service" {
  description = "(optional) - The application service to which the object belongs."
  type        = string
  default     = null
}

variable "basic_auth_realm" {
  description = "(optional) - Specifies a quoted string for the basic authentication realm. The system sends this string to a client whenever authorization fails. The default value is none"
  type        = string
  default     = null
}

variable "defaults_from" {
  description = "(optional) - Inherit defaults from parent profile"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - User defined description"
  type        = string
  default     = null
}

variable "encrypt_cookie_secret" {
  description = "(optional) - Specifies a passphrase for the cookie encryption"
  type        = string
  default     = null
}

variable "encrypt_cookies" {
  description = "(optional) - Encrypts specified cookies that the BIG-IP system sends to a client system"
  type        = set(string)
  default     = null
}

variable "fallback_host" {
  description = "(optional) - Specifies an HTTP fallback host. HTTP redirection allows you to redirect HTTP traffic to another protocol identifier, host name, port number, or URI path."
  type        = string
  default     = null
}

variable "fallback_status_codes" {
  description = "(optional) - Specifies one or more three-digit status codes that can be returned by an HTTP server."
  type        = set(string)
  default     = null
}

variable "head_erase" {
  description = "(optional) - Specifies the header string that you want to erase from an HTTP request. You can also specify none"
  type        = string
  default     = null
}

variable "head_insert" {
  description = "(optional) - Specifies a quoted header string that you want to insert into an HTTP request. You can also specify none. "
  type        = string
  default     = null
}

variable "insert_xforwarded_for" {
  description = "(optional) - When using connection pooling, which allows clients to make use of other client requests' server-side connections,\tyou can insert the X-Forwarded-For header and specify a client IP address. "
  type        = string
  default     = null
}

variable "lws_separator" {
  description = "(optional) - Specifies a quoted header string that you want to insert into an HTTP request. You can also specify none. "
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the profile"
  type        = string
}

variable "oneconnect_transformations" {
  description = "(optional) - Enables the system to perform HTTP header transformations for the purpose of  keeping server-side connections open. This feature requires configuration of a OneConnect profile."
  type        = string
  default     = null
}

variable "proxy_type" {
  description = "(optional) - Specifies the type of HTTP proxy. "
  type        = string
  default     = null
}

variable "redirect_rewrite" {
  description = "(optional) - Specifies which of the application HTTP redirects the system rewrites to HTTPS."
  type        = string
  default     = null
}

variable "request_chunking" {
  description = "(optional) - Specifies how to handle chunked and unchunked requests."
  type        = string
  default     = null
}

variable "response_chunking" {
  description = "(optional) - Specifies how to handle chunked and unchunked responses."
  type        = string
  default     = null
}

variable "response_headers_permitted" {
  description = "(optional) - Specifies headers that the BIG-IP system allows in an HTTP response."
  type        = set(string)
  default     = null
}

variable "server_agent_name" {
  description = "(optional) - Specifies the value of the Server header in responses that the BIG-IP itself generates. The default is BigIP. If no string is specified, then no Server header will be added to such responses"
  type        = string
  default     = null
}

variable "tm_partition" {
  description = "(optional) - Displays the administrative partition within which this profile resides. "
  type        = string
  default     = null
}

variable "via_host_name" {
  description = "(optional) - Specifies the hostname to include into Via header"
  type        = string
  default     = null
}

variable "via_request" {
  description = "(optional) - Specifies whether to append, remove, or preserve a Via header in an HTTP request"
  type        = string
  default     = null
}

variable "via_response" {
  description = "(optional) - Specifies whether to append, remove, or preserve a Via header in an HTTP request"
  type        = string
  default     = null
}

variable "xff_alternative_names" {
  description = "(optional) - Specifies alternative XFF headers instead of the default X-forwarded-for header"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_profile_http" "this" {
  accept_xff                 = var.accept_xff
  app_service                = var.app_service
  basic_auth_realm           = var.basic_auth_realm
  defaults_from              = var.defaults_from
  description                = var.description
  encrypt_cookie_secret      = var.encrypt_cookie_secret
  encrypt_cookies            = var.encrypt_cookies
  fallback_host              = var.fallback_host
  fallback_status_codes      = var.fallback_status_codes
  head_erase                 = var.head_erase
  head_insert                = var.head_insert
  insert_xforwarded_for      = var.insert_xforwarded_for
  lws_separator              = var.lws_separator
  name                       = var.name
  oneconnect_transformations = var.oneconnect_transformations
  proxy_type                 = var.proxy_type
  redirect_rewrite           = var.redirect_rewrite
  request_chunking           = var.request_chunking
  response_chunking          = var.response_chunking
  response_headers_permitted = var.response_headers_permitted
  server_agent_name          = var.server_agent_name
  tm_partition               = var.tm_partition
  via_host_name              = var.via_host_name
  via_request                = var.via_request
  via_response               = var.via_response
  xff_alternative_names      = var.xff_alternative_names
}
```

[top](#index)

### Outputs

```terraform
output "accept_xff" {
  description = "returns a string"
  value       = bigip_ltm_profile_http.this.accept_xff
}

output "basic_auth_realm" {
  description = "returns a string"
  value       = bigip_ltm_profile_http.this.basic_auth_realm
}

output "defaults_from" {
  description = "returns a string"
  value       = bigip_ltm_profile_http.this.defaults_from
}

output "description" {
  description = "returns a string"
  value       = bigip_ltm_profile_http.this.description
}

output "fallback_host" {
  description = "returns a string"
  value       = bigip_ltm_profile_http.this.fallback_host
}

output "head_erase" {
  description = "returns a string"
  value       = bigip_ltm_profile_http.this.head_erase
}

output "head_insert" {
  description = "returns a string"
  value       = bigip_ltm_profile_http.this.head_insert
}

output "id" {
  description = "returns a string"
  value       = bigip_ltm_profile_http.this.id
}

output "insert_xforwarded_for" {
  description = "returns a string"
  value       = bigip_ltm_profile_http.this.insert_xforwarded_for
}

output "lws_separator" {
  description = "returns a string"
  value       = bigip_ltm_profile_http.this.lws_separator
}

output "oneconnect_transformations" {
  description = "returns a string"
  value       = bigip_ltm_profile_http.this.oneconnect_transformations
}

output "proxy_type" {
  description = "returns a string"
  value       = bigip_ltm_profile_http.this.proxy_type
}

output "redirect_rewrite" {
  description = "returns a string"
  value       = bigip_ltm_profile_http.this.redirect_rewrite
}

output "request_chunking" {
  description = "returns a string"
  value       = bigip_ltm_profile_http.this.request_chunking
}

output "response_chunking" {
  description = "returns a string"
  value       = bigip_ltm_profile_http.this.response_chunking
}

output "response_headers_permitted" {
  description = "returns a set of string"
  value       = bigip_ltm_profile_http.this.response_headers_permitted
}

output "server_agent_name" {
  description = "returns a string"
  value       = bigip_ltm_profile_http.this.server_agent_name
}

output "via_host_name" {
  description = "returns a string"
  value       = bigip_ltm_profile_http.this.via_host_name
}

output "via_request" {
  description = "returns a string"
  value       = bigip_ltm_profile_http.this.via_request
}

output "via_response" {
  description = "returns a string"
  value       = bigip_ltm_profile_http.this.via_response
}

output "xff_alternative_names" {
  description = "returns a set of string"
  value       = bigip_ltm_profile_http.this.xff_alternative_names
}

output "this" {
  value = bigip_ltm_profile_http.this
}
```

[top](#index)