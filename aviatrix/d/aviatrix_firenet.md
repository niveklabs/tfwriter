# aviatrix_firenet

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_firenet" {
  source = "./modules/aviatrix/d/aviatrix_firenet"

  # vpc_id - (required) is a type of string
  vpc_id = null

  firewall_instance_association = [{
    attached             = null
    egress_interface     = null
    firenet_gw_name      = null
    firewall_name        = null
    instance_id          = null
    lan_interface        = null
    management_interface = null
    vendor_type          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "vpc_id" {
  description = "(required) - VPC ID."
  type        = string
}

variable "firewall_instance_association" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      attached             = bool
      egress_interface     = string
      firenet_gw_name      = string
      firewall_name        = string
      instance_id          = string
      lan_interface        = string
      management_interface = string
      vendor_type          = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aviatrix_firenet" "this" {
  vpc_id = var.vpc_id

  dynamic "firewall_instance_association" {
    for_each = var.firewall_instance_association
    content {
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "egress_enabled" {
  description = "returns a bool"
  value       = data.aviatrix_firenet.this.egress_enabled
}

output "hashing_algorithm" {
  description = "returns a string"
  value       = data.aviatrix_firenet.this.hashing_algorithm
}

output "id" {
  description = "returns a string"
  value       = data.aviatrix_firenet.this.id
}

output "inspection_enabled" {
  description = "returns a bool"
  value       = data.aviatrix_firenet.this.inspection_enabled
}

output "keep_alive_via_lan_interface_enabled" {
  description = "returns a bool"
  value       = data.aviatrix_firenet.this.keep_alive_via_lan_interface_enabled
}

output "this" {
  value = aviatrix_firenet.this
}
```

[top](#index)