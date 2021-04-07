# fortios_system_accprofile

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
module "fortios_system_accprofile" {
  source = "./modules/fortios/d/fortios_system_accprofile"

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
data "fortios_system_accprofile" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "admintimeout" {
  description = "returns a number"
  value       = data.fortios_system_accprofile.this.admintimeout
}

output "admintimeout_override" {
  description = "returns a string"
  value       = data.fortios_system_accprofile.this.admintimeout_override
}

output "authgrp" {
  description = "returns a string"
  value       = data.fortios_system_accprofile.this.authgrp
}

output "comments" {
  description = "returns a string"
  value       = data.fortios_system_accprofile.this.comments
}

output "ftviewgrp" {
  description = "returns a string"
  value       = data.fortios_system_accprofile.this.ftviewgrp
}

output "fwgrp" {
  description = "returns a string"
  value       = data.fortios_system_accprofile.this.fwgrp
}

output "fwgrp_permission" {
  description = "returns a list of object"
  value       = data.fortios_system_accprofile.this.fwgrp_permission
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_accprofile.this.id
}

output "loggrp" {
  description = "returns a string"
  value       = data.fortios_system_accprofile.this.loggrp
}

output "loggrp_permission" {
  description = "returns a list of object"
  value       = data.fortios_system_accprofile.this.loggrp_permission
}

output "netgrp" {
  description = "returns a string"
  value       = data.fortios_system_accprofile.this.netgrp
}

output "netgrp_permission" {
  description = "returns a list of object"
  value       = data.fortios_system_accprofile.this.netgrp_permission
}

output "scope" {
  description = "returns a string"
  value       = data.fortios_system_accprofile.this.scope
}

output "secfabgrp" {
  description = "returns a string"
  value       = data.fortios_system_accprofile.this.secfabgrp
}

output "sysgrp" {
  description = "returns a string"
  value       = data.fortios_system_accprofile.this.sysgrp
}

output "sysgrp_permission" {
  description = "returns a list of object"
  value       = data.fortios_system_accprofile.this.sysgrp_permission
}

output "system_diagnostics" {
  description = "returns a string"
  value       = data.fortios_system_accprofile.this.system_diagnostics
}

output "utmgrp" {
  description = "returns a string"
  value       = data.fortios_system_accprofile.this.utmgrp
}

output "utmgrp_permission" {
  description = "returns a list of object"
  value       = data.fortios_system_accprofile.this.utmgrp_permission
}

output "vpngrp" {
  description = "returns a string"
  value       = data.fortios_system_accprofile.this.vpngrp
}

output "wanoptgrp" {
  description = "returns a string"
  value       = data.fortios_system_accprofile.this.wanoptgrp
}

output "wifi" {
  description = "returns a string"
  value       = data.fortios_system_accprofile.this.wifi
}

output "this" {
  value = fortios_system_accprofile.this
}
```

[top](#index)