# avi_securitypolicy

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_securitypolicy" {
  source = "./modules/avi/d/avi_securitypolicy"

  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
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

### Datasource

```terraform
data "avi_securitypolicy" "this" {
  # name - (optional) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.avi_securitypolicy.this.description
}

output "dns_attacks" {
  description = "returns a set of object"
  value       = data.avi_securitypolicy.this.dns_attacks
}

output "dns_policy_index" {
  description = "returns a number"
  value       = data.avi_securitypolicy.this.dns_policy_index
}

output "id" {
  description = "returns a string"
  value       = data.avi_securitypolicy.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_securitypolicy.this.name
}

output "network_security_policy_index" {
  description = "returns a number"
  value       = data.avi_securitypolicy.this.network_security_policy_index
}

output "oper_mode" {
  description = "returns a string"
  value       = data.avi_securitypolicy.this.oper_mode
}

output "tcp_attacks" {
  description = "returns a set of object"
  value       = data.avi_securitypolicy.this.tcp_attacks
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_securitypolicy.this.tenant_ref
}

output "udp_attacks" {
  description = "returns a set of object"
  value       = data.avi_securitypolicy.this.udp_attacks
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_securitypolicy.this.uuid
}

output "this" {
  value = avi_securitypolicy.this
}
```

[top](#index)