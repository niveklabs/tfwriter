# fortios_system_csf

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
module "fortios_system_csf" {
  source = "./modules/fortios/d/fortios_system_csf"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_csf" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "accept_auth_by_cert" {
  description = "returns a string"
  value       = data.fortios_system_csf.this.accept_auth_by_cert
}

output "authorization_request_type" {
  description = "returns a string"
  value       = data.fortios_system_csf.this.authorization_request_type
}

output "certificate" {
  description = "returns a string"
  value       = data.fortios_system_csf.this.certificate
}

output "configuration_sync" {
  description = "returns a string"
  value       = data.fortios_system_csf.this.configuration_sync
}

output "fabric_device" {
  description = "returns a list of object"
  value       = data.fortios_system_csf.this.fabric_device
}

output "fabric_object_unification" {
  description = "returns a string"
  value       = data.fortios_system_csf.this.fabric_object_unification
}

output "fixed_key" {
  description = "returns a string"
  value       = data.fortios_system_csf.this.fixed_key
  sensitive   = true
}

output "group_name" {
  description = "returns a string"
  value       = data.fortios_system_csf.this.group_name
}

output "group_password" {
  description = "returns a string"
  value       = data.fortios_system_csf.this.group_password
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_csf.this.id
}

output "management_ip" {
  description = "returns a string"
  value       = data.fortios_system_csf.this.management_ip
}

output "management_port" {
  description = "returns a number"
  value       = data.fortios_system_csf.this.management_port
}

output "saml_configuration_sync" {
  description = "returns a string"
  value       = data.fortios_system_csf.this.saml_configuration_sync
}

output "status" {
  description = "returns a string"
  value       = data.fortios_system_csf.this.status
}

output "trusted_list" {
  description = "returns a list of object"
  value       = data.fortios_system_csf.this.trusted_list
}

output "upstream_ip" {
  description = "returns a string"
  value       = data.fortios_system_csf.this.upstream_ip
}

output "upstream_port" {
  description = "returns a number"
  value       = data.fortios_system_csf.this.upstream_port
}

output "this" {
  value = fortios_system_csf.this
}
```

[top](#index)