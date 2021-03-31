# fortios_system_autoinstall

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
module "fortios_system_autoinstall" {
  source = "./modules/fortios/d/fortios_system_autoinstall"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_autoinstall" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "auto_install_config" {
  description = "returns a string"
  value       = data.fortios_system_autoinstall.this.auto_install_config
}

output "auto_install_image" {
  description = "returns a string"
  value       = data.fortios_system_autoinstall.this.auto_install_image
}

output "default_config_file" {
  description = "returns a string"
  value       = data.fortios_system_autoinstall.this.default_config_file
}

output "default_image_file" {
  description = "returns a string"
  value       = data.fortios_system_autoinstall.this.default_image_file
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_autoinstall.this.id
}

output "this" {
  value = fortios_system_autoinstall.this
}
```

[top](#index)