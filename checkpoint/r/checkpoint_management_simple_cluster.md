# checkpoint_management_simple_cluster

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_simple_cluster" {
  source = "./modules/checkpoint/r/checkpoint_management_simple_cluster"

  # anti_bot - (optional) is a type of bool
  anti_bot = null
  # anti_virus - (optional) is a type of bool
  anti_virus = null
  # application_control - (optional) is a type of bool
  application_control = null
  # cluster_mode - (optional) is a type of string
  cluster_mode = null
  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # content_awareness - (optional) is a type of bool
  content_awareness = null
  # data_awareness - (optional) is a type of bool
  data_awareness = null
  # firewall - (optional) is a type of bool
  firewall = null
  # firewall_settings - (optional) is a type of map of string
  firewall_settings = {}
  # hardware - (optional) is a type of string
  hardware = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # ips - (optional) is a type of bool
  ips = null
  # ipv4_address - (optional) is a type of string
  ipv4_address = null
  # ipv6_address - (optional) is a type of string
  ipv6_address = null
  # name - (required) is a type of string
  name = null
  # os_name - (optional) is a type of string
  os_name = null
  # save_logs_locally - (optional) is a type of bool
  save_logs_locally = null
  # send_alerts_to_server - (optional) is a type of set of string
  send_alerts_to_server = []
  # send_logs_to_backup_server - (optional) is a type of set of string
  send_logs_to_backup_server = []
  # send_logs_to_server - (optional) is a type of set of string
  send_logs_to_server = []
  # tags - (optional) is a type of set of string
  tags = []
  # threat_emulation - (optional) is a type of bool
  threat_emulation = null
  # url_filtering - (optional) is a type of bool
  url_filtering = null
  # version - (optional) is a type of string
  version = null
  # vpn - (optional) is a type of bool
  vpn = null
  # vpn_settings - (optional) is a type of map of string
  vpn_settings = {}

  interfaces = [{
    anti_spoofing                  = null
    anti_spoofing_settings         = {}
    color                          = null
    comments                       = null
    interface_type                 = null
    ipv4_address                   = null
    ipv4_mask_length               = null
    ipv4_network_mask              = null
    ipv6_address                   = null
    ipv6_mask_length               = null
    ipv6_network_mask              = null
    multicast_address              = null
    multicast_address_type         = null
    name                           = null
    security_zone                  = null
    security_zone_settings         = {}
    topology                       = null
    topology_automatic_calculation = null
    topology_settings              = {}
  }]

  members = [{
    interfaces = [{
      ipv4_address      = null
      ipv4_mask_length  = null
      ipv4_network_mask = null
      ipv6_address      = null
      ipv6_mask_length  = null
      ipv6_network_mask = null
      name              = null
    }]
    ip_address        = null
    name              = null
    one_time_password = null
    sic_message       = null
    sic_name          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "anti_bot" {
  description = "(optional) - Anti-Bot blade enabled."
  type        = bool
  default     = null
}

variable "anti_virus" {
  description = "(optional) - Anti-Virus blade enabled."
  type        = bool
  default     = null
}

variable "application_control" {
  description = "(optional) - Application Control blade enabled."
  type        = bool
  default     = null
}

variable "cluster_mode" {
  description = "(optional) - Cluster mode."
  type        = string
  default     = null
}

variable "color" {
  description = "(optional) - Color of the object. Should be one of existing colors."
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional) - Comments string."
  type        = string
  default     = null
}

variable "content_awareness" {
  description = "(optional) - Content Awareness blade enabled."
  type        = bool
  default     = null
}

variable "data_awareness" {
  description = "(optional) - Data Awareness blade enabled."
  type        = bool
  default     = null
}

variable "firewall" {
  description = "(optional) - Firewall blade enabled."
  type        = bool
  default     = null
}

variable "firewall_settings" {
  description = "(optional) - Firewall settings."
  type        = map(string)
  default     = null
}

variable "hardware" {
  description = "(optional) - Cluster platform hardware."
  type        = string
  default     = null
}

variable "ignore_errors" {
  description = "(optional) - Apply changes ignoring errors. You won't be able to publish such a changes. If ignore-warnings flag was omitted - warnings will also be ignored."
  type        = bool
  default     = null
}

variable "ignore_warnings" {
  description = "(optional) - Apply changes ignoring warnings."
  type        = bool
  default     = null
}

variable "ips" {
  description = "(optional) - Intrusion Prevention System blade enabled."
  type        = bool
  default     = null
}

variable "ipv4_address" {
  description = "(optional) - IPv4 address."
  type        = string
  default     = null
}

variable "ipv6_address" {
  description = "(optional) - IPv6 address."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Object name. Should be unique in the domain."
  type        = string
}

variable "os_name" {
  description = "(optional) - OS name."
  type        = string
  default     = null
}

variable "save_logs_locally" {
  description = "(optional) - Save logs locally."
  type        = bool
  default     = null
}

variable "send_alerts_to_server" {
  description = "(optional) - Server(s) to send alerts to."
  type        = set(string)
  default     = null
}

variable "send_logs_to_backup_server" {
  description = "(optional) - Backup server(s) to send logs to."
  type        = set(string)
  default     = null
}

variable "send_logs_to_server" {
  description = "(optional) - Server(s) to send logs to."
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional) - Collection of tag identifiers."
  type        = set(string)
  default     = null
}

variable "threat_emulation" {
  description = "(optional) - Threat Emulation blade enabled."
  type        = bool
  default     = null
}

variable "url_filtering" {
  description = "(optional) - URL Filtering blade enabled."
  type        = bool
  default     = null
}

variable "version" {
  description = "(optional) - Cluster platform version."
  type        = string
  default     = null
}

variable "vpn" {
  description = "(optional) - VPN blade enabled."
  type        = bool
  default     = null
}

variable "vpn_settings" {
  description = "(optional) - Gateway VPN settings."
  type        = map(string)
  default     = null
}

variable "interfaces" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      anti_spoofing                  = bool
      anti_spoofing_settings         = map(string)
      color                          = string
      comments                       = string
      interface_type                 = string
      ipv4_address                   = string
      ipv4_mask_length               = string
      ipv4_network_mask              = string
      ipv6_address                   = string
      ipv6_mask_length               = string
      ipv6_network_mask              = string
      multicast_address              = string
      multicast_address_type         = string
      name                           = string
      security_zone                  = bool
      security_zone_settings         = map(string)
      topology                       = string
      topology_automatic_calculation = string
      topology_settings              = map(string)
    }
  ))
  default = []
}

variable "members" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      interfaces = list(object(
        {
          ipv4_address      = string
          ipv4_mask_length  = string
          ipv4_network_mask = string
          ipv6_address      = string
          ipv6_mask_length  = string
          ipv6_network_mask = string
          name              = string
        }
      ))
      ip_address        = string
      name              = string
      one_time_password = string
      sic_message       = string
      sic_name          = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_simple_cluster" "this" {
  # anti_bot - (optional) is a type of bool
  anti_bot = var.anti_bot
  # anti_virus - (optional) is a type of bool
  anti_virus = var.anti_virus
  # application_control - (optional) is a type of bool
  application_control = var.application_control
  # cluster_mode - (optional) is a type of string
  cluster_mode = var.cluster_mode
  # color - (optional) is a type of string
  color = var.color
  # comments - (optional) is a type of string
  comments = var.comments
  # content_awareness - (optional) is a type of bool
  content_awareness = var.content_awareness
  # data_awareness - (optional) is a type of bool
  data_awareness = var.data_awareness
  # firewall - (optional) is a type of bool
  firewall = var.firewall
  # firewall_settings - (optional) is a type of map of string
  firewall_settings = var.firewall_settings
  # hardware - (optional) is a type of string
  hardware = var.hardware
  # ignore_errors - (optional) is a type of bool
  ignore_errors = var.ignore_errors
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = var.ignore_warnings
  # ips - (optional) is a type of bool
  ips = var.ips
  # ipv4_address - (optional) is a type of string
  ipv4_address = var.ipv4_address
  # ipv6_address - (optional) is a type of string
  ipv6_address = var.ipv6_address
  # name - (required) is a type of string
  name = var.name
  # os_name - (optional) is a type of string
  os_name = var.os_name
  # save_logs_locally - (optional) is a type of bool
  save_logs_locally = var.save_logs_locally
  # send_alerts_to_server - (optional) is a type of set of string
  send_alerts_to_server = var.send_alerts_to_server
  # send_logs_to_backup_server - (optional) is a type of set of string
  send_logs_to_backup_server = var.send_logs_to_backup_server
  # send_logs_to_server - (optional) is a type of set of string
  send_logs_to_server = var.send_logs_to_server
  # tags - (optional) is a type of set of string
  tags = var.tags
  # threat_emulation - (optional) is a type of bool
  threat_emulation = var.threat_emulation
  # url_filtering - (optional) is a type of bool
  url_filtering = var.url_filtering
  # version - (optional) is a type of string
  version = var.version
  # vpn - (optional) is a type of bool
  vpn = var.vpn
  # vpn_settings - (optional) is a type of map of string
  vpn_settings = var.vpn_settings

  dynamic "interfaces" {
    for_each = var.interfaces
    content {
      # anti_spoofing - (optional) is a type of bool
      anti_spoofing = interfaces.value["anti_spoofing"]
      # anti_spoofing_settings - (optional) is a type of map of string
      anti_spoofing_settings = interfaces.value["anti_spoofing_settings"]
      # color - (optional) is a type of string
      color = interfaces.value["color"]
      # comments - (optional) is a type of string
      comments = interfaces.value["comments"]
      # interface_type - (required) is a type of string
      interface_type = interfaces.value["interface_type"]
      # ipv4_address - (optional) is a type of string
      ipv4_address = interfaces.value["ipv4_address"]
      # ipv4_mask_length - (optional) is a type of string
      ipv4_mask_length = interfaces.value["ipv4_mask_length"]
      # ipv4_network_mask - (optional) is a type of string
      ipv4_network_mask = interfaces.value["ipv4_network_mask"]
      # ipv6_address - (optional) is a type of string
      ipv6_address = interfaces.value["ipv6_address"]
      # ipv6_mask_length - (optional) is a type of string
      ipv6_mask_length = interfaces.value["ipv6_mask_length"]
      # ipv6_network_mask - (optional) is a type of string
      ipv6_network_mask = interfaces.value["ipv6_network_mask"]
      # multicast_address - (optional) is a type of string
      multicast_address = interfaces.value["multicast_address"]
      # multicast_address_type - (optional) is a type of string
      multicast_address_type = interfaces.value["multicast_address_type"]
      # name - (required) is a type of string
      name = interfaces.value["name"]
      # security_zone - (optional) is a type of bool
      security_zone = interfaces.value["security_zone"]
      # security_zone_settings - (optional) is a type of map of string
      security_zone_settings = interfaces.value["security_zone_settings"]
      # topology - (optional) is a type of string
      topology = interfaces.value["topology"]
      # topology_settings - (optional) is a type of map of string
      topology_settings = interfaces.value["topology_settings"]
    }
  }

  dynamic "members" {
    for_each = var.members
    content {
      # ip_address - (optional) is a type of string
      ip_address = members.value["ip_address"]
      # name - (required) is a type of string
      name = members.value["name"]
      # one_time_password - (optional) is a type of string
      one_time_password = members.value["one_time_password"]

      dynamic "interfaces" {
        for_each = members.value.interfaces
        content {
          # ipv4_address - (optional) is a type of string
          ipv4_address = interfaces.value["ipv4_address"]
          # ipv4_mask_length - (optional) is a type of string
          ipv4_mask_length = interfaces.value["ipv4_mask_length"]
          # ipv4_network_mask - (optional) is a type of string
          ipv4_network_mask = interfaces.value["ipv4_network_mask"]
          # ipv6_address - (optional) is a type of string
          ipv6_address = interfaces.value["ipv6_address"]
          # ipv6_mask_length - (optional) is a type of string
          ipv6_mask_length = interfaces.value["ipv6_mask_length"]
          # ipv6_network_mask - (optional) is a type of string
          ipv6_network_mask = interfaces.value["ipv6_network_mask"]
          # name - (required) is a type of string
          name = interfaces.value["name"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "dynamic_ip" {
  description = "returns a bool"
  value       = checkpoint_management_simple_cluster.this.dynamic_ip
}

output "id" {
  description = "returns a string"
  value       = checkpoint_management_simple_cluster.this.id
}

output "sic_name" {
  description = "returns a string"
  value       = checkpoint_management_simple_cluster.this.sic_name
}

output "sic_state" {
  description = "returns a string"
  value       = checkpoint_management_simple_cluster.this.sic_state
}

output "this" {
  value = checkpoint_management_simple_cluster.this
}
```

[top](#index)