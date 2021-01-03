# aviatrix_fqdn

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_fqdn" {
  source = "./modules/aviatrix/r/aviatrix_fqdn"

  # fqdn_enabled - (optional) is a type of bool
  fqdn_enabled = null
  # fqdn_mode - (optional) is a type of string
  fqdn_mode = null
  # fqdn_tag - (required) is a type of string
  fqdn_tag = null
  # manage_domain_names - (optional) is a type of bool
  manage_domain_names = null

  domain_names = [{
    action = null
    fqdn   = null
    port   = null
    proto  = null
  }]

  gw_filter_tag_list = [{
    gw_name        = null
    source_ip_list = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "fqdn_enabled" {
  description = "(optional) - FQDN Filter Tag Status. Valid values: true or false."
  type        = bool
  default     = null
}

variable "fqdn_mode" {
  description = "(optional) - Specify the tag color to be a white-list tag or black-list tag. 'white' or 'black'"
  type        = string
  default     = null
}

variable "fqdn_tag" {
  description = "(required) - FQDN Filter Tag Name."
  type        = string
}

variable "manage_domain_names" {
  description = "(optional) - Enable to manage domain name rules in-line. If false, domain name rules must be managed using `aviatrix_fqdn_tag_rule` resources."
  type        = bool
  default     = null
}

variable "domain_names" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = string
      fqdn   = string
      port   = string
      proto  = string
    }
  ))
  default = []
}

variable "gw_filter_tag_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      gw_name        = string
      source_ip_list = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_fqdn" "this" {
  fqdn_enabled        = var.fqdn_enabled
  fqdn_mode           = var.fqdn_mode
  fqdn_tag            = var.fqdn_tag
  manage_domain_names = var.manage_domain_names

  dynamic "domain_names" {
    for_each = var.domain_names
    content {
      action = domain_names.value["action"]
      fqdn   = domain_names.value["fqdn"]
      port   = domain_names.value["port"]
      proto  = domain_names.value["proto"]
    }
  }

  dynamic "gw_filter_tag_list" {
    for_each = var.gw_filter_tag_list
    content {
      gw_name        = gw_filter_tag_list.value["gw_name"]
      source_ip_list = gw_filter_tag_list.value["source_ip_list"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_fqdn.this.id
}

output "this" {
  value = aviatrix_fqdn.this
}
```

[top](#index)