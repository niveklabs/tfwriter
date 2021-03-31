# avi_pkiprofile

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
module "avi_pkiprofile" {
  source = "./modules/avi/d/avi_pkiprofile"

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
data "avi_pkiprofile" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "ca_certs" {
  description = "returns a list of object"
  value       = data.avi_pkiprofile.this.ca_certs
}

output "created_by" {
  description = "returns a string"
  value       = data.avi_pkiprofile.this.created_by
}

output "crl_check" {
  description = "returns a bool"
  value       = data.avi_pkiprofile.this.crl_check
}

output "crls" {
  description = "returns a list of object"
  value       = data.avi_pkiprofile.this.crls
}

output "id" {
  description = "returns a string"
  value       = data.avi_pkiprofile.this.id
}

output "ignore_peer_chain" {
  description = "returns a bool"
  value       = data.avi_pkiprofile.this.ignore_peer_chain
}

output "is_federated" {
  description = "returns a bool"
  value       = data.avi_pkiprofile.this.is_federated
}

output "name" {
  description = "returns a string"
  value       = data.avi_pkiprofile.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_pkiprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_pkiprofile.this.uuid
}

output "validate_only_leaf_crl" {
  description = "returns a bool"
  value       = data.avi_pkiprofile.this.validate_only_leaf_crl
}

output "this" {
  value = avi_pkiprofile.this
}
```

[top](#index)