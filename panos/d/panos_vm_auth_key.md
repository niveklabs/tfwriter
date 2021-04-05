# panos_vm_auth_key

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_vm_auth_key" {
  source = "./modules/panos/d/panos_vm_auth_key"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "panos_vm_auth_key" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "entries" {
  description = "returns a list of object"
  value       = data.panos_vm_auth_key.this.entries
}

output "id" {
  description = "returns a string"
  value       = data.panos_vm_auth_key.this.id
}

output "total" {
  description = "returns a number"
  value       = data.panos_vm_auth_key.this.total
}

output "this" {
  value = panos_vm_auth_key.this
}
```

[top](#index)