# bigip_bigiq_as3

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
    bigip = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_bigiq_as3" {
  source = "./modules/bigip/r/bigip_bigiq_as3"

  # as3_json - (required) is a type of string
  as3_json = null
  # bigiq_address - (required) is a type of string
  bigiq_address = null
  # bigiq_login_ref - (optional) is a type of string
  bigiq_login_ref = null
  # bigiq_password - (required) is a type of string
  bigiq_password = null
  # bigiq_port - (optional) is a type of string
  bigiq_port = null
  # bigiq_token_auth - (optional) is a type of bool
  bigiq_token_auth = null
  # bigiq_user - (required) is a type of string
  bigiq_user = null
  # tenant_list - (optional) is a type of string
  tenant_list = null
}
```

[top](#index)

### Variables

```terraform
variable "as3_json" {
  description = "(required) - AS3 json"
  type        = string
}

variable "bigiq_address" {
  description = "(required) - The registration key pool to use"
  type        = string
}

variable "bigiq_login_ref" {
  description = "(optional) - Login reference for token authentication (see BIG-IQ REST docs for details)"
  type        = string
  default     = null
}

variable "bigiq_password" {
  description = "(required) - The registration key pool to use"
  type        = string
}

variable "bigiq_port" {
  description = "(optional) - The registration key pool to use"
  type        = string
  default     = null
}

variable "bigiq_token_auth" {
  description = "(optional) - Enable to use an external authentication source (LDAP, TACACS, etc)"
  type        = bool
  default     = null
}

variable "bigiq_user" {
  description = "(required) - The registration key pool to use"
  type        = string
}

variable "tenant_list" {
  description = "(optional) - Name of Tenant"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_bigiq_as3" "this" {
  as3_json         = var.as3_json
  bigiq_address    = var.bigiq_address
  bigiq_login_ref  = var.bigiq_login_ref
  bigiq_password   = var.bigiq_password
  bigiq_port       = var.bigiq_port
  bigiq_token_auth = var.bigiq_token_auth
  bigiq_user       = var.bigiq_user
  tenant_list      = var.tenant_list
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_bigiq_as3.this.id
}

output "tenant_list" {
  description = "returns a string"
  value       = bigip_bigiq_as3.this.tenant_list
}

output "this" {
  value = bigip_bigiq_as3.this
}
```

[top](#index)