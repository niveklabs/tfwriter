# thunder_slb_template_client_ssh

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
module "thunder_slb_template_client_ssh" {
  source = "./modules/thunder/r/thunder_slb_template_client_ssh"

  # encrypted - (optional) is a type of string
  encrypted = null
  # forward_proxy_enable - (optional) is a type of number
  forward_proxy_enable = null
  # forward_proxy_hostkey - (optional) is a type of string
  forward_proxy_hostkey = null
  # name - (optional) is a type of string
  name = null
  # passphrase - (optional) is a type of string
  passphrase = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "encrypted" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forward_proxy_enable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_proxy_hostkey" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "passphrase" {
  description = "(optional)"
  type        = string
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
resource "thunder_slb_template_client_ssh" "this" {
  encrypted             = var.encrypted
  forward_proxy_enable  = var.forward_proxy_enable
  forward_proxy_hostkey = var.forward_proxy_hostkey
  name                  = var.name
  passphrase            = var.passphrase
  user_tag              = var.user_tag
  uuid                  = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_client_ssh.this.id
}

output "this" {
  value = thunder_slb_template_client_ssh.this
}
```

[top](#index)