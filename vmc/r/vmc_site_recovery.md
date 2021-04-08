# vmc_site_recovery

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
module "vmc_site_recovery" {
  source = "./modules/vmc/r/vmc_site_recovery"

  # sddc_id - (required) is a type of string
  sddc_id = null
  # srm_extension_key_suffix - (optional) is a type of string
  srm_extension_key_suffix = null

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

variable "srm_extension_key_suffix" {
  description = "(optional) - The custom extension suffix for SRM must contain 13 characters or less, be composed of letters, numbers, ., - characters only. The suffix is appended to com.vmware.vcDr- to form the full extension key. "
  type        = string
  default     = null
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
resource "vmc_site_recovery" "this" {
  # sddc_id - (required) is a type of string
  sddc_id = var.sddc_id
  # srm_extension_key_suffix - (optional) is a type of string
  srm_extension_key_suffix = var.srm_extension_key_suffix

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
  value       = vmc_site_recovery.this.id
}

output "site_recovery_state" {
  description = "returns a string"
  value       = vmc_site_recovery.this.site_recovery_state
}

output "srm_node" {
  description = "returns a map of string"
  value       = vmc_site_recovery.this.srm_node
}

output "user_id" {
  description = "returns a string"
  value       = vmc_site_recovery.this.user_id
}

output "user_name" {
  description = "returns a string"
  value       = vmc_site_recovery.this.user_name
}

output "vr_node" {
  description = "returns a map of string"
  value       = vmc_site_recovery.this.vr_node
}

output "this" {
  value = vmc_site_recovery.this
}
```

[top](#index)