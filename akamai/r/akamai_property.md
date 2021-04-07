# akamai_property

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
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_property" {
  source = "./modules/akamai/r/akamai_property"

  # contact - (optional) is a type of set of string
  contact = []
  # contract - (optional) is a type of string
  contract = null
  # contract_id - (optional) is a type of string
  contract_id = null
  # cp_code - (optional) is a type of string
  cp_code = null
  # group - (optional) is a type of string
  group = null
  # group_id - (optional) is a type of string
  group_id = null
  # is_secure - (optional) is a type of bool
  is_secure = null
  # name - (required) is a type of string
  name = null
  # product - (optional) is a type of string
  product = null
  # product_id - (optional) is a type of string
  product_id = null
  # rule_format - (optional) is a type of string
  rule_format = null
  # rules - (optional) is a type of string
  rules = null
  # variables - (optional) is a type of string
  variables = null

  hostnames = [{
    cert_provisioning_type = null
    cert_status = [{
      hostname          = null
      production_status = null
      staging_status    = null
      target            = null
    }]
    cname_from       = null
    cname_to         = null
    cname_type       = null
    edge_hostname_id = null
  }]

  origin = [{
    cache_key_hostname    = null
    compress              = null
    enable_true_client_ip = null
    forward_hostname      = null
    hostname              = null
    port                  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "contact" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "contract" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "contract_id" {
  description = "(optional) - Contract ID to be assigned to the Property"
  type        = string
  default     = null
}

variable "cp_code" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_id" {
  description = "(optional) - Group ID to be assigned to the Property"
  type        = string
  default     = null
}

variable "is_secure" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Name to give to the Property (must be unique)"
  type        = string
}

variable "product" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "product_id" {
  description = "(optional) - Product ID to be assigned to the Property"
  type        = string
  default     = null
}

variable "rule_format" {
  description = "(optional) - Specify the rule format version (defaults to latest version available when created)"
  type        = string
  default     = null
}

variable "rules" {
  description = "(optional) - Property Rules as JSON"
  type        = string
  default     = null
}

variable "variables" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostnames" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cert_provisioning_type = string
      cert_status = list(object(
        {
          hostname          = string
          production_status = string
          staging_status    = string
          target            = string
        }
      ))
      cname_from       = string
      cname_to         = string
      cname_type       = string
      edge_hostname_id = string
    }
  ))
  default = []
}

variable "origin" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cache_key_hostname    = string
      compress              = bool
      enable_true_client_ip = bool
      forward_hostname      = string
      hostname              = string
      port                  = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "akamai_property" "this" {
  # contact - (optional) is a type of set of string
  contact = var.contact
  # contract - (optional) is a type of string
  contract = var.contract
  # contract_id - (optional) is a type of string
  contract_id = var.contract_id
  # cp_code - (optional) is a type of string
  cp_code = var.cp_code
  # group - (optional) is a type of string
  group = var.group
  # group_id - (optional) is a type of string
  group_id = var.group_id
  # is_secure - (optional) is a type of bool
  is_secure = var.is_secure
  # name - (required) is a type of string
  name = var.name
  # product - (optional) is a type of string
  product = var.product
  # product_id - (optional) is a type of string
  product_id = var.product_id
  # rule_format - (optional) is a type of string
  rule_format = var.rule_format
  # rules - (optional) is a type of string
  rules = var.rules
  # variables - (optional) is a type of string
  variables = var.variables

  dynamic "hostnames" {
    for_each = var.hostnames
    content {
      # cert_provisioning_type - (required) is a type of string
      cert_provisioning_type = hostnames.value["cert_provisioning_type"]
      # cname_from - (required) is a type of string
      cname_from = hostnames.value["cname_from"]
      # cname_to - (required) is a type of string
      cname_to = hostnames.value["cname_to"]
      # cname_type - (optional) is a type of string
      cname_type = hostnames.value["cname_type"]

      dynamic "cert_status" {
        for_each = hostnames.value.cert_status
        content {
        }
      }

    }
  }

  dynamic "origin" {
    for_each = var.origin
    content {
      # cache_key_hostname - (optional) is a type of string
      cache_key_hostname = origin.value["cache_key_hostname"]
      # compress - (optional) is a type of bool
      compress = origin.value["compress"]
      # enable_true_client_ip - (optional) is a type of bool
      enable_true_client_ip = origin.value["enable_true_client_ip"]
      # forward_hostname - (optional) is a type of string
      forward_hostname = origin.value["forward_hostname"]
      # hostname - (optional) is a type of string
      hostname = origin.value["hostname"]
      # port - (optional) is a type of number
      port = origin.value["port"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "contract" {
  description = "returns a string"
  value       = akamai_property.this.contract
}

output "contract_id" {
  description = "returns a string"
  value       = akamai_property.this.contract_id
}

output "group" {
  description = "returns a string"
  value       = akamai_property.this.group
}

output "group_id" {
  description = "returns a string"
  value       = akamai_property.this.group_id
}

output "id" {
  description = "returns a string"
  value       = akamai_property.this.id
}

output "latest_version" {
  description = "returns a number"
  value       = akamai_property.this.latest_version
}

output "product" {
  description = "returns a string"
  value       = akamai_property.this.product
}

output "product_id" {
  description = "returns a string"
  value       = akamai_property.this.product_id
}

output "production_version" {
  description = "returns a number"
  value       = akamai_property.this.production_version
}

output "rule_errors" {
  description = "returns a list of object"
  value       = akamai_property.this.rule_errors
}

output "rule_format" {
  description = "returns a string"
  value       = akamai_property.this.rule_format
}

output "rule_warnings" {
  description = "returns a list of object"
  value       = akamai_property.this.rule_warnings
}

output "rules" {
  description = "returns a string"
  value       = akamai_property.this.rules
}

output "staging_version" {
  description = "returns a number"
  value       = akamai_property.this.staging_version
}

output "this" {
  value = akamai_property.this
}
```

[top](#index)