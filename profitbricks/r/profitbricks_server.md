# profitbricks_server

[back](../profitbricks.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    profitbricks = ">= 1.6.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "profitbricks_server" {
  source = "./modules/profitbricks/r/profitbricks_server"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # boot_image - (optional) is a type of string
  boot_image = null
  # cores - (required) is a type of number
  cores = null
  # cpu_family - (optional) is a type of string
  cpu_family = null
  # datacenter_id - (required) is a type of string
  datacenter_id = null
  # image_name - (optional) is a type of string
  image_name = null
  # image_password - (optional) is a type of string
  image_password = null
  # licence_type - (optional) is a type of string
  licence_type = null
  # name - (required) is a type of string
  name = null
  # ram - (required) is a type of number
  ram = null
  # ssh_key_path - (optional) is a type of list of string
  ssh_key_path = []

  nic = [{
    dhcp = null
    firewall = [{
      icmp_code        = null
      icmp_type        = null
      ip               = null
      ips              = []
      name             = null
      port_range_end   = null
      port_range_start = null
      protocol         = null
      source_ip        = null
      source_mac       = null
      target_ip        = null
    }]
    firewall_active = null
    ip              = null
    ips             = []
    lan             = null
    mac             = null
    name            = null
    nat             = null
  }]

  timeouts = [{
    create  = null
    default = null
    delete  = null
    update  = null
  }]

  volume = [{
    availability_zone = null
    bus               = null
    disk_type         = null
    image_aliases     = []
    image_name        = null
    image_password    = null
    licence_type      = null
    name              = null
    size              = null
    ssh_key_path      = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "boot_image" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cores" {
  description = "(required)"
  type        = number
}

variable "cpu_family" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "datacenter_id" {
  description = "(required)"
  type        = string
}

variable "image_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "licence_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "ram" {
  description = "(required)"
  type        = number
}

variable "ssh_key_path" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "nic" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      dhcp = bool
      firewall = list(object(
        {
          icmp_code        = string
          icmp_type        = string
          ip               = string
          ips              = list(string)
          name             = string
          port_range_end   = number
          port_range_start = number
          protocol         = string
          source_ip        = string
          source_mac       = string
          target_ip        = string
        }
      ))
      firewall_active = bool
      ip              = string
      ips             = list(string)
      lan             = number
      mac             = string
      name            = string
      nat             = bool
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create  = string
      default = string
      delete  = string
      update  = string
    }
  ))
  default = []
}

variable "volume" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      availability_zone = string
      bus               = string
      disk_type         = string
      image_aliases     = list(string)
      image_name        = string
      image_password    = string
      licence_type      = string
      name              = string
      size              = number
      ssh_key_path      = list(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "profitbricks_server" "this" {
  # availability_zone - (optional) is a type of string
  availability_zone = var.availability_zone
  # boot_image - (optional) is a type of string
  boot_image = var.boot_image
  # cores - (required) is a type of number
  cores = var.cores
  # cpu_family - (optional) is a type of string
  cpu_family = var.cpu_family
  # datacenter_id - (required) is a type of string
  datacenter_id = var.datacenter_id
  # image_name - (optional) is a type of string
  image_name = var.image_name
  # image_password - (optional) is a type of string
  image_password = var.image_password
  # licence_type - (optional) is a type of string
  licence_type = var.licence_type
  # name - (required) is a type of string
  name = var.name
  # ram - (required) is a type of number
  ram = var.ram
  # ssh_key_path - (optional) is a type of list of string
  ssh_key_path = var.ssh_key_path

  dynamic "nic" {
    for_each = var.nic
    content {
      # dhcp - (optional) is a type of bool
      dhcp = nic.value["dhcp"]
      # firewall_active - (optional) is a type of bool
      firewall_active = nic.value["firewall_active"]
      # ip - (optional) is a type of string
      ip = nic.value["ip"]
      # lan - (required) is a type of number
      lan = nic.value["lan"]
      # name - (optional) is a type of string
      name = nic.value["name"]
      # nat - (optional) is a type of bool
      nat = nic.value["nat"]

      dynamic "firewall" {
        for_each = nic.value.firewall
        content {
          # icmp_code - (optional) is a type of string
          icmp_code = firewall.value["icmp_code"]
          # icmp_type - (optional) is a type of string
          icmp_type = firewall.value["icmp_type"]
          # ip - (optional) is a type of string
          ip = firewall.value["ip"]
          # ips - (optional) is a type of list of string
          ips = firewall.value["ips"]
          # name - (optional) is a type of string
          name = firewall.value["name"]
          # port_range_end - (optional) is a type of number
          port_range_end = firewall.value["port_range_end"]
          # port_range_start - (optional) is a type of number
          port_range_start = firewall.value["port_range_start"]
          # protocol - (required) is a type of string
          protocol = firewall.value["protocol"]
          # source_ip - (optional) is a type of string
          source_ip = firewall.value["source_ip"]
          # source_mac - (optional) is a type of string
          source_mac = firewall.value["source_mac"]
          # target_ip - (optional) is a type of string
          target_ip = firewall.value["target_ip"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # default - (optional) is a type of string
      default = timeouts.value["default"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

  dynamic "volume" {
    for_each = var.volume
    content {
      # availability_zone - (optional) is a type of string
      availability_zone = volume.value["availability_zone"]
      # bus - (optional) is a type of string
      bus = volume.value["bus"]
      # disk_type - (required) is a type of string
      disk_type = volume.value["disk_type"]
      # image_name - (optional) is a type of string
      image_name = volume.value["image_name"]
      # image_password - (optional) is a type of string
      image_password = volume.value["image_password"]
      # licence_type - (optional) is a type of string
      licence_type = volume.value["licence_type"]
      # name - (optional) is a type of string
      name = volume.value["name"]
      # size - (required) is a type of number
      size = volume.value["size"]
      # ssh_key_path - (optional) is a type of list of string
      ssh_key_path = volume.value["ssh_key_path"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "boot_cdrom" {
  description = "returns a string"
  value       = profitbricks_server.this.boot_cdrom
}

output "boot_image" {
  description = "returns a string"
  value       = profitbricks_server.this.boot_image
}

output "boot_volume" {
  description = "returns a string"
  value       = profitbricks_server.this.boot_volume
}

output "cpu_family" {
  description = "returns a string"
  value       = profitbricks_server.this.cpu_family
}

output "firewallrule_id" {
  description = "returns a string"
  value       = profitbricks_server.this.firewallrule_id
}

output "id" {
  description = "returns a string"
  value       = profitbricks_server.this.id
}

output "image_name" {
  description = "returns a string"
  value       = profitbricks_server.this.image_name
}

output "image_password" {
  description = "returns a string"
  value       = profitbricks_server.this.image_password
  sensitive   = true
}

output "primary_ip" {
  description = "returns a string"
  value       = profitbricks_server.this.primary_ip
}

output "primary_nic" {
  description = "returns a string"
  value       = profitbricks_server.this.primary_nic
}

output "ssh_key_path" {
  description = "returns a list of string"
  value       = profitbricks_server.this.ssh_key_path
}

output "this" {
  value = profitbricks_server.this
}
```

[top](#index)