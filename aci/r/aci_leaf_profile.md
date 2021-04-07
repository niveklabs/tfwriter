# aci_leaf_profile

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
module "aci_leaf_profile" {
  source = "./modules/aci/r/aci_leaf_profile"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # leaf_selector_ids - (optional) is a type of list of string
  leaf_selector_ids = []
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # node_block_ids - (optional) is a type of list of string
  node_block_ids = []
  # relation_infra_rs_acc_card_p - (optional) is a type of set of string
  relation_infra_rs_acc_card_p = []
  # relation_infra_rs_acc_port_p - (optional) is a type of set of string
  relation_infra_rs_acc_port_p = []

  leaf_selector = [{
    description = null
    id          = null
    name        = null
    node_block = [{
      description = null
      from_       = null
      id          = null
      name        = null
      to_         = null
    }]
    switch_association_type = null
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

variable "leaf_selector_ids" {
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

variable "node_block_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "relation_infra_rs_acc_card_p" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relation_infra_rs_acc_port_p" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "leaf_selector" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      id          = string
      name        = string
      node_block = list(object(
        {
          description = string
          from_       = string
          id          = string
          name        = string
          to_         = string
        }
      ))
      switch_association_type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aci_leaf_profile" "this" {
  annotation                   = var.annotation
  description                  = var.description
  leaf_selector_ids            = var.leaf_selector_ids
  name                         = var.name
  name_alias                   = var.name_alias
  node_block_ids               = var.node_block_ids
  relation_infra_rs_acc_card_p = var.relation_infra_rs_acc_card_p
  relation_infra_rs_acc_port_p = var.relation_infra_rs_acc_port_p

  dynamic "leaf_selector" {
    for_each = var.leaf_selector
    content {
      # description - (optional) is a type of string
      description = leaf_selector.value["description"]
      # id - (optional) is a type of string
      id = leaf_selector.value["id"]
      # name - (required) is a type of string
      name = leaf_selector.value["name"]
      # switch_association_type - (required) is a type of string
      switch_association_type = leaf_selector.value["switch_association_type"]

      dynamic "node_block" {
        for_each = leaf_selector.value.node_block
        content {
          # description - (optional) is a type of string
          description = node_block.value["description"]
          # from_ - (optional) is a type of string
          from_ = node_block.value["from_"]
          # id - (optional) is a type of string
          id = node_block.value["id"]
          # name - (required) is a type of string
          name = node_block.value["name"]
          # to_ - (optional) is a type of string
          to_ = node_block.value["to_"]
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
  value       = aci_leaf_profile.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_leaf_profile.this.id
}

output "leaf_selector_ids" {
  description = "returns a list of string"
  value       = aci_leaf_profile.this.leaf_selector_ids
}

output "name_alias" {
  description = "returns a string"
  value       = aci_leaf_profile.this.name_alias
}

output "node_block_ids" {
  description = "returns a list of string"
  value       = aci_leaf_profile.this.node_block_ids
}

output "this" {
  value = aci_leaf_profile.this
}
```

[top](#index)