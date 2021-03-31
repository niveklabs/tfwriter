# aci_contract

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
module "aci_contract" {
  source = "./modules/aci/r/aci_contract"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # filter_entry_ids - (optional) is a type of list of string
  filter_entry_ids = []
  # filter_ids - (optional) is a type of list of string
  filter_ids = []
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # prio - (optional) is a type of string
  prio = null
  # relation_vz_rs_graph_att - (optional) is a type of string
  relation_vz_rs_graph_att = null
  # scope - (optional) is a type of string
  scope = null
  # target_dscp - (optional) is a type of string
  target_dscp = null
  # tenant_dn - (required) is a type of string
  tenant_dn = null

  filter = [{
    annotation  = null
    description = null
    filter_entry = [{
      apply_to_frag     = null
      arp_opc           = null
      d_from_port       = null
      d_to_port         = null
      entry_annotation  = null
      entry_description = null
      entry_name_alias  = null
      ether_t           = null
      filter_entry_name = null
      icmpv4_t          = null
      icmpv6_t          = null
      id                = null
      match_dscp        = null
      prot              = null
      s_from_port       = null
      s_to_port         = null
      stateful          = null
      tcp_rules         = null
    }]
    filter_name = null
    id          = null
    name_alias  = null
  }]
}
```

[top](#index)

### Variables

```terraform
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

variable "filter_entry_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "filter_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "prio" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_vz_rs_graph_att" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_dscp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_dn" {
  description = "(required)"
  type        = string
}

variable "filter" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      annotation  = string
      description = string
      filter_entry = list(object(
        {
          apply_to_frag     = string
          arp_opc           = string
          d_from_port       = string
          d_to_port         = string
          entry_annotation  = string
          entry_description = string
          entry_name_alias  = string
          ether_t           = string
          filter_entry_name = string
          icmpv4_t          = string
          icmpv6_t          = string
          id                = string
          match_dscp        = string
          prot              = string
          s_from_port       = string
          s_to_port         = string
          stateful          = string
          tcp_rules         = string
        }
      ))
      filter_name = string
      id          = string
      name_alias  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aci_contract" "this" {
  annotation               = var.annotation
  description              = var.description
  filter_entry_ids         = var.filter_entry_ids
  filter_ids               = var.filter_ids
  name                     = var.name
  name_alias               = var.name_alias
  prio                     = var.prio
  relation_vz_rs_graph_att = var.relation_vz_rs_graph_att
  scope                    = var.scope
  target_dscp              = var.target_dscp
  tenant_dn                = var.tenant_dn

  dynamic "filter" {
    for_each = var.filter
    content {
      annotation  = filter.value["annotation"]
      description = filter.value["description"]
      filter_name = filter.value["filter_name"]
      name_alias  = filter.value["name_alias"]

      dynamic "filter_entry" {
        for_each = filter.value.filter_entry
        content {
          apply_to_frag     = filter_entry.value["apply_to_frag"]
          arp_opc           = filter_entry.value["arp_opc"]
          d_from_port       = filter_entry.value["d_from_port"]
          d_to_port         = filter_entry.value["d_to_port"]
          entry_annotation  = filter_entry.value["entry_annotation"]
          entry_description = filter_entry.value["entry_description"]
          entry_name_alias  = filter_entry.value["entry_name_alias"]
          ether_t           = filter_entry.value["ether_t"]
          filter_entry_name = filter_entry.value["filter_entry_name"]
          icmpv4_t          = filter_entry.value["icmpv4_t"]
          icmpv6_t          = filter_entry.value["icmpv6_t"]
          match_dscp        = filter_entry.value["match_dscp"]
          prot              = filter_entry.value["prot"]
          s_from_port       = filter_entry.value["s_from_port"]
          s_to_port         = filter_entry.value["s_to_port"]
          stateful          = filter_entry.value["stateful"]
          tcp_rules         = filter_entry.value["tcp_rules"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_contract.this.description
}

output "filter_entry_ids" {
  description = "returns a list of string"
  value       = aci_contract.this.filter_entry_ids
}

output "filter_ids" {
  description = "returns a list of string"
  value       = aci_contract.this.filter_ids
}

output "id" {
  description = "returns a string"
  value       = aci_contract.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_contract.this.name_alias
}

output "prio" {
  description = "returns a string"
  value       = aci_contract.this.prio
}

output "scope" {
  description = "returns a string"
  value       = aci_contract.this.scope
}

output "target_dscp" {
  description = "returns a string"
  value       = aci_contract.this.target_dscp
}

output "this" {
  value = aci_contract.this
}
```

[top](#index)