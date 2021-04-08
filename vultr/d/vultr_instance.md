# vultr_instance

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
module "vultr_instance" {
  source = "./modules/vultr/d/vultr_instance"


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
data "vultr_instance" "this" {

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
output "allowed_bandwidth" {
  description = "returns a number"
  value       = data.vultr_instance.this.allowed_bandwidth
}

output "app_id" {
  description = "returns a number"
  value       = data.vultr_instance.this.app_id
}

output "backups" {
  description = "returns a string"
  value       = data.vultr_instance.this.backups
}

output "date_created" {
  description = "returns a string"
  value       = data.vultr_instance.this.date_created
}

output "disk" {
  description = "returns a number"
  value       = data.vultr_instance.this.disk
}

output "features" {
  description = "returns a list of string"
  value       = data.vultr_instance.this.features
}

output "firewall_group_id" {
  description = "returns a string"
  value       = data.vultr_instance.this.firewall_group_id
}

output "gateway_v4" {
  description = "returns a string"
  value       = data.vultr_instance.this.gateway_v4
}

output "id" {
  description = "returns a string"
  value       = data.vultr_instance.this.id
}

output "internal_ip" {
  description = "returns a string"
  value       = data.vultr_instance.this.internal_ip
}

output "kvm" {
  description = "returns a string"
  value       = data.vultr_instance.this.kvm
}

output "label" {
  description = "returns a string"
  value       = data.vultr_instance.this.label
}

output "location" {
  description = "returns a string"
  value       = data.vultr_instance.this.location
}

output "main_ip" {
  description = "returns a string"
  value       = data.vultr_instance.this.main_ip
}

output "netmask_v4" {
  description = "returns a string"
  value       = data.vultr_instance.this.netmask_v4
}

output "os" {
  description = "returns a string"
  value       = data.vultr_instance.this.os
}

output "os_id" {
  description = "returns a number"
  value       = data.vultr_instance.this.os_id
}

output "plan" {
  description = "returns a string"
  value       = data.vultr_instance.this.plan
}

output "power_status" {
  description = "returns a string"
  value       = data.vultr_instance.this.power_status
}

output "ram" {
  description = "returns a number"
  value       = data.vultr_instance.this.ram
}

output "region" {
  description = "returns a string"
  value       = data.vultr_instance.this.region
}

output "server_status" {
  description = "returns a string"
  value       = data.vultr_instance.this.server_status
}

output "status" {
  description = "returns a string"
  value       = data.vultr_instance.this.status
}

output "tag" {
  description = "returns a string"
  value       = data.vultr_instance.this.tag
}

output "v6_main_ip" {
  description = "returns a string"
  value       = data.vultr_instance.this.v6_main_ip
}

output "v6_network" {
  description = "returns a string"
  value       = data.vultr_instance.this.v6_network
}

output "v6_network_size" {
  description = "returns a number"
  value       = data.vultr_instance.this.v6_network_size
}

output "vcpu_count" {
  description = "returns a number"
  value       = data.vultr_instance.this.vcpu_count
}

output "this" {
  value = vultr_instance.this
}
```

[top](#index)