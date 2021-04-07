# thunder_slb_template_persist_cookie

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_slb_template_persist_cookie" {
  source = "./modules/thunder/r/thunder_slb_template_persist_cookie"

  # cookie_name - (optional) is a type of string
  cookie_name = null
  # domain - (optional) is a type of string
  domain = null
  # dont_honor_conn_rules - (optional) is a type of number
  dont_honor_conn_rules = null
  # encrypt_level - (optional) is a type of number
  encrypt_level = null
  # encrypted - (optional) is a type of string
  encrypted = null
  # expire - (optional) is a type of number
  expire = null
  # httponly - (optional) is a type of number
  httponly = null
  # insert_always - (optional) is a type of number
  insert_always = null
  # match_type - (optional) is a type of number
  match_type = null
  # name - (optional) is a type of string
  name = null
  # pass_phrase - (optional) is a type of string
  pass_phrase = null
  # pass_thru - (optional) is a type of number
  pass_thru = null
  # path - (optional) is a type of string
  path = null
  # scan_all_members - (optional) is a type of number
  scan_all_members = null
  # secure - (optional) is a type of number
  secure = null
  # server - (optional) is a type of number
  server = null
  # server_service_group - (optional) is a type of number
  server_service_group = null
  # service_group - (optional) is a type of number
  service_group = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "cookie_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dont_honor_conn_rules" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "encrypt_level" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "encrypted" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expire" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "httponly" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "insert_always" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "match_type" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pass_phrase" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pass_thru" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scan_all_members" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "secure" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "server" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "server_service_group" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "service_group" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_persist_cookie" "this" {
  # cookie_name - (optional) is a type of string
  cookie_name = var.cookie_name
  # domain - (optional) is a type of string
  domain = var.domain
  # dont_honor_conn_rules - (optional) is a type of number
  dont_honor_conn_rules = var.dont_honor_conn_rules
  # encrypt_level - (optional) is a type of number
  encrypt_level = var.encrypt_level
  # encrypted - (optional) is a type of string
  encrypted = var.encrypted
  # expire - (optional) is a type of number
  expire = var.expire
  # httponly - (optional) is a type of number
  httponly = var.httponly
  # insert_always - (optional) is a type of number
  insert_always = var.insert_always
  # match_type - (optional) is a type of number
  match_type = var.match_type
  # name - (optional) is a type of string
  name = var.name
  # pass_phrase - (optional) is a type of string
  pass_phrase = var.pass_phrase
  # pass_thru - (optional) is a type of number
  pass_thru = var.pass_thru
  # path - (optional) is a type of string
  path = var.path
  # scan_all_members - (optional) is a type of number
  scan_all_members = var.scan_all_members
  # secure - (optional) is a type of number
  secure = var.secure
  # server - (optional) is a type of number
  server = var.server
  # server_service_group - (optional) is a type of number
  server_service_group = var.server_service_group
  # service_group - (optional) is a type of number
  service_group = var.service_group
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_persist_cookie.this.id
}

output "this" {
  value = thunder_slb_template_persist_cookie.this
}
```

[top](#index)