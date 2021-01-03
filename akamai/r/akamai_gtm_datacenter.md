# akamai_gtm_datacenter

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_gtm_datacenter" {
  source = "./modules/akamai/r/akamai_gtm_datacenter"

  # city - (optional) is a type of string
  city = null
  # clone_of - (optional) is a type of number
  clone_of = null
  # cloud_server_host_header_override - (optional) is a type of bool
  cloud_server_host_header_override = null
  # cloud_server_targeting - (optional) is a type of bool
  cloud_server_targeting = null
  # continent - (optional) is a type of string
  continent = null
  # country - (optional) is a type of string
  country = null
  # domain - (required) is a type of string
  domain = null
  # latitude - (optional) is a type of number
  latitude = null
  # longitude - (optional) is a type of number
  longitude = null
  # nickname - (optional) is a type of string
  nickname = null
  # state_or_province - (optional) is a type of string
  state_or_province = null
  # wait_on_complete - (optional) is a type of bool
  wait_on_complete = null

  default_load_object = [{
    load_object      = null
    load_object_port = null
    load_servers     = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "city" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "clone_of" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cloud_server_host_header_override" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cloud_server_targeting" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "continent" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "country" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain" {
  description = "(required)"
  type        = string
}

variable "latitude" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "longitude" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "nickname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state_or_province" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wait_on_complete" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "default_load_object" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      load_object      = string
      load_object_port = number
      load_servers     = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "akamai_gtm_datacenter" "this" {
  city                              = var.city
  clone_of                          = var.clone_of
  cloud_server_host_header_override = var.cloud_server_host_header_override
  cloud_server_targeting            = var.cloud_server_targeting
  continent                         = var.continent
  country                           = var.country
  domain                            = var.domain
  latitude                          = var.latitude
  longitude                         = var.longitude
  nickname                          = var.nickname
  state_or_province                 = var.state_or_province
  wait_on_complete                  = var.wait_on_complete

  dynamic "default_load_object" {
    for_each = var.default_load_object
    content {
      load_object      = default_load_object.value["load_object"]
      load_object_port = default_load_object.value["load_object_port"]
      load_servers     = default_load_object.value["load_servers"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "datacenter_id" {
  description = "returns a number"
  value       = akamai_gtm_datacenter.this.datacenter_id
}

output "id" {
  description = "returns a string"
  value       = akamai_gtm_datacenter.this.id
}

output "ping_interval" {
  description = "returns a number"
  value       = akamai_gtm_datacenter.this.ping_interval
}

output "ping_packet_size" {
  description = "returns a number"
  value       = akamai_gtm_datacenter.this.ping_packet_size
}

output "score_penalty" {
  description = "returns a number"
  value       = akamai_gtm_datacenter.this.score_penalty
}

output "servermonitor_liveness_count" {
  description = "returns a number"
  value       = akamai_gtm_datacenter.this.servermonitor_liveness_count
}

output "servermonitor_load_count" {
  description = "returns a number"
  value       = akamai_gtm_datacenter.this.servermonitor_load_count
}

output "servermonitor_pool" {
  description = "returns a string"
  value       = akamai_gtm_datacenter.this.servermonitor_pool
}

output "virtual" {
  description = "returns a bool"
  value       = akamai_gtm_datacenter.this.virtual
}

output "this" {
  value = akamai_gtm_datacenter.this
}
```

[top](#index)