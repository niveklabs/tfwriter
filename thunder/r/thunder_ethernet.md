# thunder_ethernet

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_ethernet" {
  source = "./modules/thunder/r/thunder_ethernet"


  ethernet_list = [{
    action       = null
    duplexity    = null
    flow_control = null
    ifnum        = null
    ip = [{
      address_list = [{
        ipv4_address = null
        ipv4_netmask = null
      }]
      dhcp = null
      uuid = null
    }]
    l3_vlan_fwd_disable = null
    load_interval       = null
    mtu                 = null
    speed               = null
    trap_source         = null
    uuid                = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "ethernet_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action       = string
      duplexity    = string
      flow_control = number
      ifnum        = number
      ip = list(object(
        {
          address_list = list(object(
            {
              ipv4_address = string
              ipv4_netmask = string
            }
          ))
          dhcp = number
          uuid = string
        }
      ))
      l3_vlan_fwd_disable = number
      load_interval       = number
      mtu                 = number
      speed               = string
      trap_source         = number
      uuid                = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_ethernet" "this" {

  dynamic "ethernet_list" {
    for_each = var.ethernet_list
    content {
      action              = ethernet_list.value["action"]
      duplexity           = ethernet_list.value["duplexity"]
      flow_control        = ethernet_list.value["flow_control"]
      ifnum               = ethernet_list.value["ifnum"]
      l3_vlan_fwd_disable = ethernet_list.value["l3_vlan_fwd_disable"]
      load_interval       = ethernet_list.value["load_interval"]
      mtu                 = ethernet_list.value["mtu"]
      speed               = ethernet_list.value["speed"]
      trap_source         = ethernet_list.value["trap_source"]
      uuid                = ethernet_list.value["uuid"]

      dynamic "ip" {
        for_each = ethernet_list.value.ip
        content {
          dhcp = ip.value["dhcp"]
          uuid = ip.value["uuid"]

          dynamic "address_list" {
            for_each = ip.value.address_list
            content {
              ipv4_address = address_list.value["ipv4_address"]
              ipv4_netmask = address_list.value["ipv4_netmask"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_ethernet.this.id
}

output "this" {
  value = thunder_ethernet.this
}
```

[top](#index)