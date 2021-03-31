# fortios_system_ndproxy

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_ndproxy" {
  source = "./modules/fortios/d/fortios_system_ndproxy"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_ndproxy" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_system_ndproxy.this.id
}

output "member" {
  description = "returns a list of object"
  value       = data.fortios_system_ndproxy.this.member
}

output "status" {
  description = "returns a string"
  value       = data.fortios_system_ndproxy.this.status
}

output "this" {
  value = fortios_system_ndproxy.this
}
```

[top](#index)