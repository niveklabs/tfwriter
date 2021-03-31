# ecl_baremetal_availability_zone_v2

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
    ecl = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_baremetal_availability_zone_v2" {
  source = "./modules/ecl/d/ecl_baremetal_availability_zone_v2"

  # zone_name - (optional) is a type of string
  zone_name = null
}
```

[top](#index)

### Variables

```terraform
variable "zone_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ecl_baremetal_availability_zone_v2" "this" {
  zone_name = var.zone_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.ecl_baremetal_availability_zone_v2.this.id
}

output "zone_name" {
  description = "returns a string"
  value       = data.ecl_baremetal_availability_zone_v2.this.zone_name
}

output "this" {
  value = ecl_baremetal_availability_zone_v2.this
}
```

[top](#index)