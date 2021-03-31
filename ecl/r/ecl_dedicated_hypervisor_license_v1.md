# ecl_dedicated_hypervisor_license_v1

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
    ecl = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_dedicated_hypervisor_license_v1" {
  source = "./modules/ecl/r/ecl_dedicated_hypervisor_license_v1"

  # license_type - (required) is a type of string
  license_type = null
}
```

[top](#index)

### Variables

```terraform
variable "license_type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ecl_dedicated_hypervisor_license_v1" "this" {
  license_type = var.license_type
}
```

[top](#index)

### Outputs

```terraform
output "assigned_from" {
  description = "returns a string"
  value       = ecl_dedicated_hypervisor_license_v1.this.assigned_from
}

output "expires_at" {
  description = "returns a string"
  value       = ecl_dedicated_hypervisor_license_v1.this.expires_at
}

output "id" {
  description = "returns a string"
  value       = ecl_dedicated_hypervisor_license_v1.this.id
}

output "key" {
  description = "returns a string"
  value       = ecl_dedicated_hypervisor_license_v1.this.key
}

output "this" {
  value = ecl_dedicated_hypervisor_license_v1.this
}
```

[top](#index)