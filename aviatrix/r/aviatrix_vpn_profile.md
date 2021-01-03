# aviatrix_vpn_profile

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_vpn_profile" {
  source = "./modules/aviatrix/r/aviatrix_vpn_profile"

  # base_rule - (optional) is a type of string
  base_rule = null
  # manage_user_attachment - (optional) is a type of bool
  manage_user_attachment = null
  # name - (required) is a type of string
  name = null
  # users - (optional) is a type of list of string
  users = []

  policy = [{
    action = null
    port   = null
    proto  = null
    target = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "base_rule" {
  description = "(optional) - Base policy rule of the profile to be added. Enter 'allow_all' or 'deny_all'."
  type        = string
  default     = null
}

variable "manage_user_attachment" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - name for the VPN profile."
  type        = string
}

variable "users" {
  description = "(optional) - List of VPN users to attach to this profile."
  type        = list(string)
  default     = null
}

variable "policy" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = string
      port   = string
      proto  = string
      target = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_vpn_profile" "this" {
  base_rule              = var.base_rule
  manage_user_attachment = var.manage_user_attachment
  name                   = var.name
  users                  = var.users

  dynamic "policy" {
    for_each = var.policy
    content {
      action = policy.value["action"]
      port   = policy.value["port"]
      proto  = policy.value["proto"]
      target = policy.value["target"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_vpn_profile.this.id
}

output "this" {
  value = aviatrix_vpn_profile.this
}
```

[top](#index)