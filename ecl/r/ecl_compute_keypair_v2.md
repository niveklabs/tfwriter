# ecl_compute_keypair_v2

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
module "ecl_compute_keypair_v2" {
  source = "./modules/ecl/r/ecl_compute_keypair_v2"

  # name - (required) is a type of string
  name = null
  # public_key - (optional) is a type of string
  public_key = null
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

variable "public_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "ecl_compute_keypair_v2" "this" {
  # name - (required) is a type of string
  name = var.name
  # public_key - (optional) is a type of string
  public_key = var.public_key
  # region - (optional) is a type of string
  region = var.region
}
```

[top](#index)

### Outputs

```terraform
output "fingerprint" {
  description = "returns a string"
  value       = ecl_compute_keypair_v2.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = ecl_compute_keypair_v2.this.id
}

output "private_key" {
  description = "returns a string"
  value       = ecl_compute_keypair_v2.this.private_key
}

output "public_key" {
  description = "returns a string"
  value       = ecl_compute_keypair_v2.this.public_key
}

output "region" {
  description = "returns a string"
  value       = ecl_compute_keypair_v2.this.region
}

output "this" {
  value = ecl_compute_keypair_v2.this
}
```

[top](#index)