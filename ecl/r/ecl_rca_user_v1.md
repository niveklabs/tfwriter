# ecl_rca_user_v1

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
module "ecl_rca_user_v1" {
  source = "./modules/ecl/r/ecl_rca_user_v1"

  # password - (required) is a type of string
  password = null
}
```

[top](#index)

### Variables

```terraform
variable "password" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ecl_rca_user_v1" "this" {
  password = var.password
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ecl_rca_user_v1.this.id
}

output "name" {
  description = "returns a string"
  value       = ecl_rca_user_v1.this.name
}

output "vpn_endpoints" {
  description = "returns a list of object"
  value       = ecl_rca_user_v1.this.vpn_endpoints
}

output "this" {
  value = ecl_rca_user_v1.this
}
```

[top](#index)