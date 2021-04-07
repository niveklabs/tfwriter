# fortios_system_apiuser

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
module "fortios_system_apiuser" {
  source = "./modules/fortios/d/fortios_system_apiuser"

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
data "fortios_system_apiuser" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "accprofile" {
  description = "returns a string"
  value       = data.fortios_system_apiuser.this.accprofile
}

output "api_key" {
  description = "returns a string"
  value       = data.fortios_system_apiuser.this.api_key
  sensitive   = true
}

output "comments" {
  description = "returns a string"
  value       = data.fortios_system_apiuser.this.comments
}

output "cors_allow_origin" {
  description = "returns a string"
  value       = data.fortios_system_apiuser.this.cors_allow_origin
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_apiuser.this.id
}

output "peer_auth" {
  description = "returns a string"
  value       = data.fortios_system_apiuser.this.peer_auth
}

output "peer_group" {
  description = "returns a string"
  value       = data.fortios_system_apiuser.this.peer_group
}

output "schedule" {
  description = "returns a string"
  value       = data.fortios_system_apiuser.this.schedule
}

output "trusthost" {
  description = "returns a list of object"
  value       = data.fortios_system_apiuser.this.trusthost
}

output "vdom" {
  description = "returns a list of object"
  value       = data.fortios_system_apiuser.this.vdom
}

output "this" {
  value = fortios_system_apiuser.this
}
```

[top](#index)