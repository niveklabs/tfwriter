# cloudflare_spectrum_application

[back](../cloudflare.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudflare = ">= 2.15.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_spectrum_application" {
  source = "./modules/cloudflare/r/cloudflare_spectrum_application"

  # argo_smart_routing - (optional) is a type of bool
  argo_smart_routing = null
  # edge_ip_connectivity - (optional) is a type of string
  edge_ip_connectivity = null
  # edge_ips - (optional) is a type of list of string
  edge_ips = []
  # ip_firewall - (optional) is a type of bool
  ip_firewall = null
  # origin_direct - (optional) is a type of list of string
  origin_direct = []
  # origin_port - (optional) is a type of number
  origin_port = null
  # protocol - (required) is a type of string
  protocol = null
  # proxy_protocol - (optional) is a type of string
  proxy_protocol = null
  # tls - (optional) is a type of string
  tls = null
  # traffic_type - (optional) is a type of string
  traffic_type = null
  # zone_id - (required) is a type of string
  zone_id = null

  dns = [{
    name = null
    type = null
  }]

  origin_dns = [{
    name = null
  }]

  origin_port_range = [{
    end   = null
    start = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "argo_smart_routing" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "edge_ip_connectivity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "edge_ips" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "ip_firewall" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "origin_direct" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "origin_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "proxy_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tls" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "traffic_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(required)"
  type        = string
}

variable "dns" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      name = string
      type = string
    }
  ))
}

variable "origin_dns" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "origin_port_range" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      end   = number
      start = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_spectrum_application" "this" {
  argo_smart_routing   = var.argo_smart_routing
  edge_ip_connectivity = var.edge_ip_connectivity
  edge_ips             = var.edge_ips
  ip_firewall          = var.ip_firewall
  origin_direct        = var.origin_direct
  origin_port          = var.origin_port
  protocol             = var.protocol
  proxy_protocol       = var.proxy_protocol
  tls                  = var.tls
  traffic_type         = var.traffic_type
  zone_id              = var.zone_id

  dynamic "dns" {
    for_each = var.dns
    content {
      name = dns.value["name"]
      type = dns.value["type"]
    }
  }

  dynamic "origin_dns" {
    for_each = var.origin_dns
    content {
      name = origin_dns.value["name"]
    }
  }

  dynamic "origin_port_range" {
    for_each = var.origin_port_range
    content {
      end   = origin_port_range.value["end"]
      start = origin_port_range.value["start"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_spectrum_application.this.id
}

output "this" {
  value = cloudflare_spectrum_application.this
}
```

[top](#index)