# aci_l3_ext_subnet

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_l3_ext_subnet" {
  source = "./modules/aci/r/aci_l3_ext_subnet"

  # aggregate - (optional) is a type of string
  aggregate = null
  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # external_network_instance_profile_dn - (required) is a type of string
  external_network_instance_profile_dn = null
  # ip - (required) is a type of string
  ip = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # relation_l3ext_rs_subnet_to_rt_summ - (optional) is a type of string
  relation_l3ext_rs_subnet_to_rt_summ = null
  # scope - (optional) is a type of list of string
  scope = []

  relation_l3ext_rs_subnet_to_profile = [{
    direction              = null
    tn_rtctrl_profile_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "aggregate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "external_network_instance_profile_dn" {
  description = "(required)"
  type        = string
}

variable "ip" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_l3ext_rs_subnet_to_rt_summ" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "relation_l3ext_rs_subnet_to_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      direction              = string
      tn_rtctrl_profile_name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aci_l3_ext_subnet" "this" {
  # aggregate - (optional) is a type of string
  aggregate = var.aggregate
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # description - (optional) is a type of string
  description = var.description
  # external_network_instance_profile_dn - (required) is a type of string
  external_network_instance_profile_dn = var.external_network_instance_profile_dn
  # ip - (required) is a type of string
  ip = var.ip
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # relation_l3ext_rs_subnet_to_rt_summ - (optional) is a type of string
  relation_l3ext_rs_subnet_to_rt_summ = var.relation_l3ext_rs_subnet_to_rt_summ
  # scope - (optional) is a type of list of string
  scope = var.scope

  dynamic "relation_l3ext_rs_subnet_to_profile" {
    for_each = var.relation_l3ext_rs_subnet_to_profile
    content {
      # direction - (required) is a type of string
      direction = relation_l3ext_rs_subnet_to_profile.value["direction"]
      # tn_rtctrl_profile_name - (required) is a type of string
      tn_rtctrl_profile_name = relation_l3ext_rs_subnet_to_profile.value["tn_rtctrl_profile_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "aggregate" {
  description = "returns a string"
  value       = aci_l3_ext_subnet.this.aggregate
}

output "description" {
  description = "returns a string"
  value       = aci_l3_ext_subnet.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_l3_ext_subnet.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_l3_ext_subnet.this.name_alias
}

output "scope" {
  description = "returns a list of string"
  value       = aci_l3_ext_subnet.this.scope
}

output "this" {
  value = aci_l3_ext_subnet.this
}
```

[top](#index)