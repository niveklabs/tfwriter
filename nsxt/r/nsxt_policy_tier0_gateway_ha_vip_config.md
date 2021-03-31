# nsxt_policy_tier0_gateway_ha_vip_config

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_tier0_gateway_ha_vip_config" {
  source = "./modules/nsxt/r/nsxt_policy_tier0_gateway_ha_vip_config"


  config = [{
    enabled                  = null
    external_interface_paths = []
    vip_subnets              = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "config" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      enabled                  = bool
      external_interface_paths = list(string)
      vip_subnets              = list(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_policy_tier0_gateway_ha_vip_config" "this" {

  dynamic "config" {
    for_each = var.config
    content {
      enabled                  = config.value["enabled"]
      external_interface_paths = config.value["external_interface_paths"]
      vip_subnets              = config.value["vip_subnets"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = nsxt_policy_tier0_gateway_ha_vip_config.this.id
}

output "locale_service_id" {
  description = "returns a string"
  value       = nsxt_policy_tier0_gateway_ha_vip_config.this.locale_service_id
}

output "tier0_id" {
  description = "returns a string"
  value       = nsxt_policy_tier0_gateway_ha_vip_config.this.tier0_id
}

output "this" {
  value = nsxt_policy_tier0_gateway_ha_vip_config.this
}
```

[top](#index)