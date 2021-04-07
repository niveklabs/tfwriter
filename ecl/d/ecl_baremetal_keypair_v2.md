# ecl_baremetal_keypair_v2

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
module "ecl_baremetal_keypair_v2" {
  source = "./modules/ecl/d/ecl_baremetal_keypair_v2"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "ecl_baremetal_keypair_v2" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "fingerprint" {
  description = "returns a string"
  value       = data.ecl_baremetal_keypair_v2.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = data.ecl_baremetal_keypair_v2.this.id
}

output "public_key" {
  description = "returns a string"
  value       = data.ecl_baremetal_keypair_v2.this.public_key
}

output "this" {
  value = ecl_baremetal_keypair_v2.this
}
```

[top](#index)