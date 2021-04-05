# ecl_compute_keypair_v2

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "ecl_compute_keypair_v2" {
  source = "./modules/ecl/d/ecl_compute_keypair_v2"

  # name - (required) is a type of string
  name = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ecl_compute_keypair_v2" "this" {
  name   = var.name
  region = var.region
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.ecl_compute_keypair_v2.this.id
}

output "public_key" {
  description = "returns a string"
  value       = data.ecl_compute_keypair_v2.this.public_key
}

output "region" {
  description = "returns a string"
  value       = data.ecl_compute_keypair_v2.this.region
}

output "this" {
  value = ecl_compute_keypair_v2.this
}
```

[top](#index)