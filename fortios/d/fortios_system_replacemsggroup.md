# fortios_system_replacemsggroup

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
module "fortios_system_replacemsggroup" {
  source = "./modules/fortios/d/fortios_system_replacemsggroup"

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
data "fortios_system_replacemsggroup" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "admin" {
  description = "returns a list of object"
  value       = data.fortios_system_replacemsggroup.this.admin
}

output "alertmail" {
  description = "returns a list of object"
  value       = data.fortios_system_replacemsggroup.this.alertmail
}

output "auth" {
  description = "returns a list of object"
  value       = data.fortios_system_replacemsggroup.this.auth
}

output "automation" {
  description = "returns a list of object"
  value       = data.fortios_system_replacemsggroup.this.automation
}

output "comment" {
  description = "returns a string"
  value       = data.fortios_system_replacemsggroup.this.comment
}

output "custom_message" {
  description = "returns a list of object"
  value       = data.fortios_system_replacemsggroup.this.custom_message
}

output "device_detection_portal" {
  description = "returns a list of object"
  value       = data.fortios_system_replacemsggroup.this.device_detection_portal
}

output "ec" {
  description = "returns a list of object"
  value       = data.fortios_system_replacemsggroup.this.ec
}

output "fortiguard_wf" {
  description = "returns a list of object"
  value       = data.fortios_system_replacemsggroup.this.fortiguard_wf
}

output "ftp" {
  description = "returns a list of object"
  value       = data.fortios_system_replacemsggroup.this.ftp
}

output "group_type" {
  description = "returns a string"
  value       = data.fortios_system_replacemsggroup.this.group_type
}

output "http" {
  description = "returns a list of object"
  value       = data.fortios_system_replacemsggroup.this.http
}

output "icap" {
  description = "returns a list of object"
  value       = data.fortios_system_replacemsggroup.this.icap
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_replacemsggroup.this.id
}

output "mail" {
  description = "returns a list of object"
  value       = data.fortios_system_replacemsggroup.this.mail
}

output "nac_quar" {
  description = "returns a list of object"
  value       = data.fortios_system_replacemsggroup.this.nac_quar
}

output "nntp" {
  description = "returns a list of object"
  value       = data.fortios_system_replacemsggroup.this.nntp
}

output "spam" {
  description = "returns a list of object"
  value       = data.fortios_system_replacemsggroup.this.spam
}

output "sslvpn" {
  description = "returns a list of object"
  value       = data.fortios_system_replacemsggroup.this.sslvpn
}

output "traffic_quota" {
  description = "returns a list of object"
  value       = data.fortios_system_replacemsggroup.this.traffic_quota
}

output "utm" {
  description = "returns a list of object"
  value       = data.fortios_system_replacemsggroup.this.utm
}

output "webproxy" {
  description = "returns a list of object"
  value       = data.fortios_system_replacemsggroup.this.webproxy
}

output "this" {
  value = fortios_system_replacemsggroup.this
}
```

[top](#index)