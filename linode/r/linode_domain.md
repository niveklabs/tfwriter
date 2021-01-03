# linode_domain

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
    linode = ">= 1.13.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_domain" {
  source = "./modules/linode/r/linode_domain"

  # axfr_ips - (optional) is a type of set of string
  axfr_ips = []
  # description - (optional) is a type of string
  description = null
  # domain - (required) is a type of string
  domain = null
  # expire_sec - (optional) is a type of number
  expire_sec = null
  # group - (optional) is a type of string
  group = null
  # master_ips - (optional) is a type of set of string
  master_ips = []
  # refresh_sec - (optional) is a type of number
  refresh_sec = null
  # retry_sec - (optional) is a type of number
  retry_sec = null
  # soa_email - (optional) is a type of string
  soa_email = null
  # status - (optional) is a type of string
  status = null
  # tags - (optional) is a type of set of string
  tags = []
  # ttl_sec - (optional) is a type of number
  ttl_sec = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "axfr_ips" {
  description = "(optional) - The list of IPs that may perform a zone transfer for this Domain. This is potentially dangerous, and should be set to an empty list unless you intend to use it."
  type        = set(string)
  default     = null
}

variable "description" {
  description = "(optional) - A description for this Domain. This is for display purposes only."
  type        = string
  default     = null
}

variable "domain" {
  description = "(required) - The domain this Domain represents. These must be unique in our system; you cannot have two Domains representing the same domain."
  type        = string
}

variable "expire_sec" {
  description = "(optional) - The amount of time in seconds that may pass before this Domain is no longer authoritative. Valid values are 0, 300, 3600, 7200, 14400, 28800, 57600, 86400, 172800, 345600, 604800, 1209600, and 2419200 - any other value will be rounded to the nearest valid value."
  type        = number
  default     = null
}

variable "group" {
  description = "(optional) - The group this Domain belongs to. This is for display purposes only."
  type        = string
  default     = null
}

variable "master_ips" {
  description = "(optional) - The IP addresses representing the master DNS for this Domain."
  type        = set(string)
  default     = null
}

variable "refresh_sec" {
  description = "(optional) - The amount of time in seconds before this Domain should be refreshed. Valid values are 0, 300, 3600, 7200, 14400, 28800, 57600, 86400, 172800, 345600, 604800, 1209600, and 2419200 - any other value will be rounded to the nearest valid value."
  type        = number
  default     = null
}

variable "retry_sec" {
  description = "(optional) - The interval, in seconds, at which a failed refresh should be retried. Valid values are 0, 300, 3600, 7200, 14400, 28800, 57600, 86400, 172800, 345600, 604800, 1209600, and 2419200 - any other value will be rounded to the nearest valid value."
  type        = number
  default     = null
}

variable "soa_email" {
  description = "(optional) - Start of Authority email address. This is required for master Domains."
  type        = string
  default     = null
}

variable "status" {
  description = "(optional) - Used to control whether this Domain is currently being rendered."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - An array of tags applied to this object. Tags are for organizational purposes only."
  type        = set(string)
  default     = null
}

variable "ttl_sec" {
  description = "(optional) - 'Time to Live' - the amount of time in seconds that this Domain's records may be cached by resolvers or other domain servers. Valid values are 0, 300, 3600, 7200, 14400, 28800, 57600, 86400, 172800, 345600, 604800, 1209600, and 2419200 - any other value will be rounded to the nearest valid value."
  type        = number
  default     = null
}

variable "type" {
  description = "(required) - If this Domain represents the authoritative source of information for the domain it describes, or if it is a read-only copy of a master (also called a slave)."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "linode_domain" "this" {
  axfr_ips    = var.axfr_ips
  description = var.description
  domain      = var.domain
  expire_sec  = var.expire_sec
  group       = var.group
  master_ips  = var.master_ips
  refresh_sec = var.refresh_sec
  retry_sec   = var.retry_sec
  soa_email   = var.soa_email
  status      = var.status
  tags        = var.tags
  ttl_sec     = var.ttl_sec
  type        = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = linode_domain.this.id
}

output "status" {
  description = "returns a string"
  value       = linode_domain.this.status
}

output "this" {
  value = linode_domain.this
}
```

[top](#index)