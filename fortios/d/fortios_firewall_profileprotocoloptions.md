# fortios_firewall_profileprotocoloptions

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
module "fortios_firewall_profileprotocoloptions" {
  source = "./modules/fortios/d/fortios_firewall_profileprotocoloptions"

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
data "fortios_firewall_profileprotocoloptions" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "cifs" {
  description = "returns a list of object"
  value       = data.fortios_firewall_profileprotocoloptions.this.cifs
}

output "comment" {
  description = "returns a string"
  value       = data.fortios_firewall_profileprotocoloptions.this.comment
}

output "dns" {
  description = "returns a list of object"
  value       = data.fortios_firewall_profileprotocoloptions.this.dns
}

output "feature_set" {
  description = "returns a string"
  value       = data.fortios_firewall_profileprotocoloptions.this.feature_set
}

output "ftp" {
  description = "returns a list of object"
  value       = data.fortios_firewall_profileprotocoloptions.this.ftp
}

output "http" {
  description = "returns a list of object"
  value       = data.fortios_firewall_profileprotocoloptions.this.http
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_profileprotocoloptions.this.id
}

output "imap" {
  description = "returns a list of object"
  value       = data.fortios_firewall_profileprotocoloptions.this.imap
}

output "mail_signature" {
  description = "returns a list of object"
  value       = data.fortios_firewall_profileprotocoloptions.this.mail_signature
}

output "mapi" {
  description = "returns a list of object"
  value       = data.fortios_firewall_profileprotocoloptions.this.mapi
}

output "nntp" {
  description = "returns a list of object"
  value       = data.fortios_firewall_profileprotocoloptions.this.nntp
}

output "oversize_log" {
  description = "returns a string"
  value       = data.fortios_firewall_profileprotocoloptions.this.oversize_log
}

output "pop3" {
  description = "returns a list of object"
  value       = data.fortios_firewall_profileprotocoloptions.this.pop3
}

output "replacemsg_group" {
  description = "returns a string"
  value       = data.fortios_firewall_profileprotocoloptions.this.replacemsg_group
}

output "rpc_over_http" {
  description = "returns a string"
  value       = data.fortios_firewall_profileprotocoloptions.this.rpc_over_http
}

output "smtp" {
  description = "returns a list of object"
  value       = data.fortios_firewall_profileprotocoloptions.this.smtp
}

output "ssh" {
  description = "returns a list of object"
  value       = data.fortios_firewall_profileprotocoloptions.this.ssh
}

output "switching_protocols_log" {
  description = "returns a string"
  value       = data.fortios_firewall_profileprotocoloptions.this.switching_protocols_log
}

output "this" {
  value = fortios_firewall_profileprotocoloptions.this
}
```

[top](#index)