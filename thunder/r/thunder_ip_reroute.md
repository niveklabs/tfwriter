# thunder_ip_reroute

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
module "thunder_ip_reroute" {
  source = "./modules/thunder/r/thunder_ip_reroute"

  # uuid - (optional) is a type of string
  uuid = null

  suppress_protocols = [{
    connected = null
    ebgp      = null
    ibgp      = null
    isis      = null
    ospf      = null
    rip       = null
    static    = null
    uuid      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "suppress_protocols" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      connected = number
      ebgp      = number
      ibgp      = number
      isis      = number
      ospf      = number
      rip       = number
      static    = number
      uuid      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_ip_reroute" "this" {
  uuid = var.uuid

  dynamic "suppress_protocols" {
    for_each = var.suppress_protocols
    content {
      connected = suppress_protocols.value["connected"]
      ebgp      = suppress_protocols.value["ebgp"]
      ibgp      = suppress_protocols.value["ibgp"]
      isis      = suppress_protocols.value["isis"]
      ospf      = suppress_protocols.value["ospf"]
      rip       = suppress_protocols.value["rip"]
      static    = suppress_protocols.value["static"]
      uuid      = suppress_protocols.value["uuid"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_ip_reroute.this.id
}

output "this" {
  value = thunder_ip_reroute.this
}
```

[top](#index)