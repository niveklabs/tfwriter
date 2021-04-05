# nutanix_karbon_private_registries

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_karbon_private_registries" {
  source = "./modules/nutanix/d/nutanix_karbon_private_registries"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "nutanix_karbon_private_registries" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.nutanix_karbon_private_registries.this.id
}

output "private_registries" {
  description = "returns a list of object"
  value       = data.nutanix_karbon_private_registries.this.private_registries
}

output "this" {
  value = nutanix_karbon_private_registries.this
}
```

[top](#index)