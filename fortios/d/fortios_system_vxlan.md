# fortios_system_vxlan

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
module "fortios_system_vxlan" {
  source = "./modules/fortios/d/fortios_system_vxlan"

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
data "fortios_system_vxlan" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "dstport" {
  description = "returns a number"
  value       = data.fortios_system_vxlan.this.dstport
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_vxlan.this.id
}

output "interface" {
  description = "returns a string"
  value       = data.fortios_system_vxlan.this.interface
}

output "ip_version" {
  description = "returns a string"
  value       = data.fortios_system_vxlan.this.ip_version
}

output "multicast_ttl" {
  description = "returns a number"
  value       = data.fortios_system_vxlan.this.multicast_ttl
}

output "remote_ip" {
  description = "returns a list of object"
  value       = data.fortios_system_vxlan.this.remote_ip
}

output "remote_ip6" {
  description = "returns a list of object"
  value       = data.fortios_system_vxlan.this.remote_ip6
}

output "vni" {
  description = "returns a number"
  value       = data.fortios_system_vxlan.this.vni
}

output "this" {
  value = fortios_system_vxlan.this
}
```

[top](#index)