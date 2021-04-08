# vultr_bare_metal_server

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vultr = ">= 2.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vultr_bare_metal_server" {
  source = "./modules/vultr/d/vultr_bare_metal_server"


  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "vultr_bare_metal_server" "this" {

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # values - (required) is a type of list of string
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "app_id" {
  description = "returns a number"
  value       = data.vultr_bare_metal_server.this.app_id
}

output "cpu_count" {
  description = "returns a number"
  value       = data.vultr_bare_metal_server.this.cpu_count
}

output "date_created" {
  description = "returns a string"
  value       = data.vultr_bare_metal_server.this.date_created
}

output "disk" {
  description = "returns a string"
  value       = data.vultr_bare_metal_server.this.disk
}

output "features" {
  description = "returns a list of string"
  value       = data.vultr_bare_metal_server.this.features
}

output "gateway_v4" {
  description = "returns a string"
  value       = data.vultr_bare_metal_server.this.gateway_v4
}

output "id" {
  description = "returns a string"
  value       = data.vultr_bare_metal_server.this.id
}

output "label" {
  description = "returns a string"
  value       = data.vultr_bare_metal_server.this.label
}

output "mac_address" {
  description = "returns a string"
  value       = data.vultr_bare_metal_server.this.mac_address
}

output "main_ip" {
  description = "returns a string"
  value       = data.vultr_bare_metal_server.this.main_ip
}

output "netmask_v4" {
  description = "returns a string"
  value       = data.vultr_bare_metal_server.this.netmask_v4
}

output "os" {
  description = "returns a string"
  value       = data.vultr_bare_metal_server.this.os
}

output "os_id" {
  description = "returns a number"
  value       = data.vultr_bare_metal_server.this.os_id
}

output "plan" {
  description = "returns a string"
  value       = data.vultr_bare_metal_server.this.plan
}

output "ram" {
  description = "returns a string"
  value       = data.vultr_bare_metal_server.this.ram
}

output "region" {
  description = "returns a string"
  value       = data.vultr_bare_metal_server.this.region
}

output "status" {
  description = "returns a string"
  value       = data.vultr_bare_metal_server.this.status
}

output "tag" {
  description = "returns a string"
  value       = data.vultr_bare_metal_server.this.tag
}

output "v6_main_ip" {
  description = "returns a string"
  value       = data.vultr_bare_metal_server.this.v6_main_ip
}

output "v6_network" {
  description = "returns a string"
  value       = data.vultr_bare_metal_server.this.v6_network
}

output "v6_network_size" {
  description = "returns a number"
  value       = data.vultr_bare_metal_server.this.v6_network_size
}

output "this" {
  value = vultr_bare_metal_server.this
}
```

[top](#index)