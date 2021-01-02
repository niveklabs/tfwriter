# vsphere_vm_storage_policy

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vsphere = ">= 1.24.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_vm_storage_policy" {
  source = "./modules/vsphere/r/vsphere_vm_storage_policy"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null

  tag_rules = [{
    include_datastores_with_tags = null
    tag_category                 = null
    tags                         = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the storage policy."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the storage policy."
  type        = string
}

variable "tag_rules" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      include_datastores_with_tags = bool
      tag_category                 = string
      tags                         = list(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_vm_storage_policy" "this" {
  description = var.description
  name        = var.name

  dynamic "tag_rules" {
    for_each = var.tag_rules
    content {
      include_datastores_with_tags = tag_rules.value["include_datastores_with_tags"]
      tag_category                 = tag_rules.value["tag_category"]
      tags                         = tag_rules.value["tags"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_vm_storage_policy.this.id
}

output "this" {
  value = vsphere_vm_storage_policy.this
}
```

[top](#index)