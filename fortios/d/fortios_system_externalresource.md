# fortios_system_externalresource

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
module "fortios_system_externalresource" {
  source = "./modules/fortios/d/fortios_system_externalresource"

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
data "fortios_system_externalresource" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "category" {
  description = "returns a number"
  value       = data.fortios_system_externalresource.this.category
}

output "comments" {
  description = "returns a string"
  value       = data.fortios_system_externalresource.this.comments
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_externalresource.this.id
}

output "interface" {
  description = "returns a string"
  value       = data.fortios_system_externalresource.this.interface
}

output "interface_select_method" {
  description = "returns a string"
  value       = data.fortios_system_externalresource.this.interface_select_method
}

output "password" {
  description = "returns a string"
  value       = data.fortios_system_externalresource.this.password
  sensitive   = true
}

output "refresh_rate" {
  description = "returns a number"
  value       = data.fortios_system_externalresource.this.refresh_rate
}

output "resource" {
  description = "returns a string"
  value       = data.fortios_system_externalresource.this.resource
}

output "source_ip" {
  description = "returns a string"
  value       = data.fortios_system_externalresource.this.source_ip
}

output "status" {
  description = "returns a string"
  value       = data.fortios_system_externalresource.this.status
}

output "type" {
  description = "returns a string"
  value       = data.fortios_system_externalresource.this.type
}

output "user_agent" {
  description = "returns a string"
  value       = data.fortios_system_externalresource.this.user_agent
}

output "username" {
  description = "returns a string"
  value       = data.fortios_system_externalresource.this.username
}

output "uuid" {
  description = "returns a string"
  value       = data.fortios_system_externalresource.this.uuid
}

output "this" {
  value = fortios_system_externalresource.this
}
```

[top](#index)