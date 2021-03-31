# avi_systemconfiguration

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_systemconfiguration" {
  source = "./modules/avi/d/avi_systemconfiguration"

  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "avi_systemconfiguration" "this" {
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "admin_auth_configuration" {
  description = "returns a set of object"
  value       = data.avi_systemconfiguration.this.admin_auth_configuration
}

output "default_license_tier" {
  description = "returns a string"
  value       = data.avi_systemconfiguration.this.default_license_tier
}

output "dns_configuration" {
  description = "returns a set of object"
  value       = data.avi_systemconfiguration.this.dns_configuration
}

output "dns_virtualservice_refs" {
  description = "returns a list of string"
  value       = data.avi_systemconfiguration.this.dns_virtualservice_refs
}

output "docker_mode" {
  description = "returns a bool"
  value       = data.avi_systemconfiguration.this.docker_mode
}

output "email_configuration" {
  description = "returns a set of object"
  value       = data.avi_systemconfiguration.this.email_configuration
}

output "global_tenant_config" {
  description = "returns a set of object"
  value       = data.avi_systemconfiguration.this.global_tenant_config
}

output "id" {
  description = "returns a string"
  value       = data.avi_systemconfiguration.this.id
}

output "linux_configuration" {
  description = "returns a set of object"
  value       = data.avi_systemconfiguration.this.linux_configuration
}

output "mgmt_ip_access_control" {
  description = "returns a set of object"
  value       = data.avi_systemconfiguration.this.mgmt_ip_access_control
}

output "ntp_configuration" {
  description = "returns a set of object"
  value       = data.avi_systemconfiguration.this.ntp_configuration
}

output "portal_configuration" {
  description = "returns a set of object"
  value       = data.avi_systemconfiguration.this.portal_configuration
}

output "proxy_configuration" {
  description = "returns a set of object"
  value       = data.avi_systemconfiguration.this.proxy_configuration
}

output "secure_channel_configuration" {
  description = "returns a set of object"
  value       = data.avi_systemconfiguration.this.secure_channel_configuration
}

output "snmp_configuration" {
  description = "returns a set of object"
  value       = data.avi_systemconfiguration.this.snmp_configuration
}

output "ssh_ciphers" {
  description = "returns a list of string"
  value       = data.avi_systemconfiguration.this.ssh_ciphers
}

output "ssh_hmacs" {
  description = "returns a list of string"
  value       = data.avi_systemconfiguration.this.ssh_hmacs
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_systemconfiguration.this.uuid
}

output "welcome_workflow_complete" {
  description = "returns a bool"
  value       = data.avi_systemconfiguration.this.welcome_workflow_complete
}

output "this" {
  value = avi_systemconfiguration.this
}
```

[top](#index)