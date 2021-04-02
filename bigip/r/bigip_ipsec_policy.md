# bigip_ipsec_policy

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
module "bigip_ipsec_policy" {
  source = "./modules/bigip/r/bigip_ipsec_policy"

  # auth_algorithm - (optional) is a type of string
  auth_algorithm = null
  # description - (optional) is a type of string
  description = null
  # encrypt_algorithm - (optional) is a type of string
  encrypt_algorithm = null
  # ipcomp - (optional) is a type of string
  ipcomp = null
  # kb_lifetime - (optional) is a type of number
  kb_lifetime = null
  # lifetime - (optional) is a type of number
  lifetime = null
  # mode - (optional) is a type of string
  mode = null
  # name - (required) is a type of string
  name = null
  # perfect_forward_secrecy - (optional) is a type of string
  perfect_forward_secrecy = null
  # protocol - (optional) is a type of string
  protocol = null
  # tunnel_local_address - (optional) is a type of string
  tunnel_local_address = null
  # tunnel_remote_address - (optional) is a type of string
  tunnel_remote_address = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_algorithm" {
  description = "(optional) - Specifies the algorithm to use for IKE authentication."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Description of the IPsec policy."
  type        = string
  default     = null
}

variable "encrypt_algorithm" {
  description = "(optional) - Specifies the algorithm to use for IKE encryption."
  type        = string
  default     = null
}

variable "ipcomp" {
  description = "(optional) - Specifies whether to use IPComp encapsulation."
  type        = string
  default     = null
}

variable "kb_lifetime" {
  description = "(optional) - Specifies the length of time before the IKE security association expires, in kilobytes."
  type        = number
  default     = null
}

variable "lifetime" {
  description = "(optional) - Specifies the length of time before the IKE security association expires, in minutes."
  type        = number
  default     = null
}

variable "mode" {
  description = "(optional) - Specifies the processing mode."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Specifies the name of the IPsec policy"
  type        = string
}

variable "perfect_forward_secrecy" {
  description = "(optional) - Specifies the Diffie-Hellman group to use for IKE Phase 2 negotiation."
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional) - Specifies the IPsec protocol."
  type        = string
  default     = null
}

variable "tunnel_local_address" {
  description = "(optional) - Specifies the local endpoint IP address of the IPsec tunnel. This parameter is only valid when mode is tunnel."
  type        = string
  default     = null
}

variable "tunnel_remote_address" {
  description = "(optional) - Specifies the remote endpoint IP address of the IPsec tunnel. This parameter is only valid when mode is tunnel."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ipsec_policy" "this" {
  auth_algorithm          = var.auth_algorithm
  description             = var.description
  encrypt_algorithm       = var.encrypt_algorithm
  ipcomp                  = var.ipcomp
  kb_lifetime             = var.kb_lifetime
  lifetime                = var.lifetime
  mode                    = var.mode
  name                    = var.name
  perfect_forward_secrecy = var.perfect_forward_secrecy
  protocol                = var.protocol
  tunnel_local_address    = var.tunnel_local_address
  tunnel_remote_address   = var.tunnel_remote_address
}
```

[top](#index)

### Outputs

```terraform
output "auth_algorithm" {
  description = "returns a string"
  value       = bigip_ipsec_policy.this.auth_algorithm
}

output "description" {
  description = "returns a string"
  value       = bigip_ipsec_policy.this.description
}

output "encrypt_algorithm" {
  description = "returns a string"
  value       = bigip_ipsec_policy.this.encrypt_algorithm
}

output "id" {
  description = "returns a string"
  value       = bigip_ipsec_policy.this.id
}

output "ipcomp" {
  description = "returns a string"
  value       = bigip_ipsec_policy.this.ipcomp
}

output "kb_lifetime" {
  description = "returns a number"
  value       = bigip_ipsec_policy.this.kb_lifetime
}

output "lifetime" {
  description = "returns a number"
  value       = bigip_ipsec_policy.this.lifetime
}

output "mode" {
  description = "returns a string"
  value       = bigip_ipsec_policy.this.mode
}

output "perfect_forward_secrecy" {
  description = "returns a string"
  value       = bigip_ipsec_policy.this.perfect_forward_secrecy
}

output "protocol" {
  description = "returns a string"
  value       = bigip_ipsec_policy.this.protocol
}

output "tunnel_local_address" {
  description = "returns a string"
  value       = bigip_ipsec_policy.this.tunnel_local_address
}

output "tunnel_remote_address" {
  description = "returns a string"
  value       = bigip_ipsec_policy.this.tunnel_remote_address
}

output "this" {
  value = bigip_ipsec_policy.this
}
```

[top](#index)