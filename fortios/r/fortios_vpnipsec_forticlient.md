# fortios_vpnipsec_forticlient

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_vpnipsec_forticlient" {
  source = "./modules/fortios/r/fortios_vpnipsec_forticlient"

  # phase2name - (required) is a type of string
  phase2name = null
  # realm - (optional) is a type of string
  realm = null
  # status - (optional) is a type of string
  status = null
  # usergroupname - (required) is a type of string
  usergroupname = null
}
```

[top](#index)

### Variables

```terraform
variable "phase2name" {
  description = "(required)"
  type        = string
}

variable "realm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "usergroupname" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_vpnipsec_forticlient" "this" {
  phase2name    = var.phase2name
  realm         = var.realm
  status        = var.status
  usergroupname = var.usergroupname
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_vpnipsec_forticlient.this.id
}

output "realm" {
  description = "returns a string"
  value       = fortios_vpnipsec_forticlient.this.realm
}

output "status" {
  description = "returns a string"
  value       = fortios_vpnipsec_forticlient.this.status
}

output "this" {
  value = fortios_vpnipsec_forticlient.this
}
```

[top](#index)