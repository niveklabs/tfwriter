# panos_system_info

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
module "panos_system_info" {
  source = "./modules/panos/d/panos_system_info"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "panos_system_info" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.panos_system_info.this.id
}

output "info" {
  description = "returns a map of string"
  value       = data.panos_system_info.this.info
}

output "version_major" {
  description = "returns a number"
  value       = data.panos_system_info.this.version_major
}

output "version_minor" {
  description = "returns a number"
  value       = data.panos_system_info.this.version_minor
}

output "version_patch" {
  description = "returns a number"
  value       = data.panos_system_info.this.version_patch
}

output "this" {
  value = panos_system_info.this
}
```

[top](#index)