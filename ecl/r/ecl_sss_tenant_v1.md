# ecl_sss_tenant_v1

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
module "ecl_sss_tenant_v1" {
  source = "./modules/ecl/r/ecl_sss_tenant_v1"

  # contract_id - (optional) is a type of string
  contract_id = null
  # description - (required) is a type of string
  description = null
  # tenant_name - (required) is a type of string
  tenant_name = null
  # tenant_region - (required) is a type of string
  tenant_region = null
}
```

[top](#index)

### Variables

```terraform
variable "contract_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(required)"
  type        = string
}

variable "tenant_name" {
  description = "(required)"
  type        = string
}

variable "tenant_region" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ecl_sss_tenant_v1" "this" {
  # contract_id - (optional) is a type of string
  contract_id = var.contract_id
  # description - (required) is a type of string
  description = var.description
  # tenant_name - (required) is a type of string
  tenant_name = var.tenant_name
  # tenant_region - (required) is a type of string
  tenant_region = var.tenant_region
}
```

[top](#index)

### Outputs

```terraform
output "contract_id" {
  description = "returns a string"
  value       = ecl_sss_tenant_v1.this.contract_id
}

output "id" {
  description = "returns a string"
  value       = ecl_sss_tenant_v1.this.id
}

output "start_time" {
  description = "returns a string"
  value       = ecl_sss_tenant_v1.this.start_time
}

output "tenant_id" {
  description = "returns a string"
  value       = ecl_sss_tenant_v1.this.tenant_id
}

output "this" {
  value = ecl_sss_tenant_v1.this
}
```

[top](#index)