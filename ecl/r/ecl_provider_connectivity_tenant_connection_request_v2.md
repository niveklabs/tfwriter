# ecl_provider_connectivity_tenant_connection_request_v2

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_provider_connectivity_tenant_connection_request_v2" {
  source = "./modules/ecl/r/ecl_provider_connectivity_tenant_connection_request_v2"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # network_id - (required) is a type of string
  network_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # tenant_id_other - (required) is a type of string
  tenant_id_other = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tenant_id_other" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ecl_provider_connectivity_tenant_connection_request_v2" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (optional) is a type of string
  name = var.name
  # network_id - (required) is a type of string
  network_id = var.network_id
  # tags - (optional) is a type of map of string
  tags = var.tags
  # tenant_id_other - (required) is a type of string
  tenant_id_other = var.tenant_id_other
}
```

[top](#index)

### Outputs

```terraform
output "approval_request_id" {
  description = "returns a string"
  value       = ecl_provider_connectivity_tenant_connection_request_v2.this.approval_request_id
}

output "id" {
  description = "returns a string"
  value       = ecl_provider_connectivity_tenant_connection_request_v2.this.id
}

output "name" {
  description = "returns a string"
  value       = ecl_provider_connectivity_tenant_connection_request_v2.this.name
}

output "status" {
  description = "returns a string"
  value       = ecl_provider_connectivity_tenant_connection_request_v2.this.status
}

output "tenant_id" {
  description = "returns a string"
  value       = ecl_provider_connectivity_tenant_connection_request_v2.this.tenant_id
}

output "this" {
  value = ecl_provider_connectivity_tenant_connection_request_v2.this
}
```

[top](#index)