# linode_domain_record

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.16.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_domain_record" {
  source = "./modules/linode/r/linode_domain_record"

  # domain_id - (required) is a type of number
  domain_id = null
  # name - (optional) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null
  # priority - (optional) is a type of number
  priority = null
  # protocol - (optional) is a type of string
  protocol = null
  # record_type - (required) is a type of string
  record_type = null
  # service - (optional) is a type of string
  service = null
  # tag - (optional) is a type of string
  tag = null
  # target - (required) is a type of string
  target = null
  # ttl_sec - (optional) is a type of number
  ttl_sec = null
  # weight - (optional) is a type of number
  weight = null
}
```

[top](#index)

### Variables

```terraform
variable "domain_id" {
  description = "(required) - The ID of the Domain to access."
  type        = number
}

variable "name" {
  description = "(optional) - The name of this Record. This field's actual usage depends on the type of record this represents. For A and AAAA records, this is the subdomain being associated with an IP address. Generated for SRV records."
  type        = string
  default     = null
}

variable "port" {
  description = "(optional) - The port this Record points to."
  type        = number
  default     = null
}

variable "priority" {
  description = "(optional) - The priority of the target host. Lower values are preferred."
  type        = number
  default     = null
}

variable "protocol" {
  description = "(optional) - The protocol this Record's service communicates with. Only valid for SRV records."
  type        = string
  default     = null
}

variable "record_type" {
  description = "(required) - The type of Record this is in the DNS system. For example, A records associate a domain name with an IPv4 address, and AAAA records associate a domain name with an IPv6 address."
  type        = string
}

variable "service" {
  description = "(optional) - The service this Record identified. Only valid for SRV records."
  type        = string
  default     = null
}

variable "tag" {
  description = "(optional) - The tag portion of a CAA record. It is invalid to set this on other record types."
  type        = string
  default     = null
}

variable "target" {
  description = "(required) - The target for this Record. This field's actual usage depends on the type of record this represents. For A and AAAA records, this is the address the named Domain should resolve to."
  type        = string
}

variable "ttl_sec" {
  description = "(optional) - 'Time to Live' - the amount of time in seconds that this Domain's records may be cached by resolvers or other domain servers. Valid values are 0, 300, 3600, 7200, 14400, 28800, 57600, 86400, 172800, 345600, 604800, 1209600, and 2419200 - any other value will be rounded to the nearest valid value."
  type        = number
  default     = null
}

variable "weight" {
  description = "(optional) - The relative weight of this Record. Higher values are preferred."
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "linode_domain_record" "this" {
  domain_id   = var.domain_id
  name        = var.name
  port        = var.port
  priority    = var.priority
  protocol    = var.protocol
  record_type = var.record_type
  service     = var.service
  tag         = var.tag
  target      = var.target
  ttl_sec     = var.ttl_sec
  weight      = var.weight
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = linode_domain_record.this.id
}

output "name" {
  description = "returns a string"
  value       = linode_domain_record.this.name
}

output "this" {
  value = linode_domain_record.this
}
```

[top](#index)