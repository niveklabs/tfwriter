# vmc_srm_node

[back](../vmc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vmc = ">= 1.5.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vmc_srm_node" {
  source = "./modules/vmc/r/vmc_srm_node"

  # sddc_id - (required) is a type of string
  sddc_id = null
  # srm_node_extension_key_suffix - (required) is a type of string
  srm_node_extension_key_suffix = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "sddc_id" {
  description = "(required) - SDDC identifier"
  type        = string
}

variable "srm_node_extension_key_suffix" {
  description = "(required) - The custom extension suffix for SRM must contain 13 characters or less, be composed of letters, numbers, ., - characters only. The suffix is appended to com.vmware.vcDr- to form the full extension key. "
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vmc_srm_node" "this" {
  # sddc_id - (required) is a type of string
  sddc_id = var.sddc_id
  # srm_node_extension_key_suffix - (required) is a type of string
  srm_node_extension_key_suffix = var.srm_node_extension_key_suffix

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vmc_srm_node.this.id
}

output "srm_instance" {
  description = "returns a map of string"
  value       = vmc_srm_node.this.srm_instance
}

output "this" {
  value = vmc_srm_node.this
}
```

[top](#index)