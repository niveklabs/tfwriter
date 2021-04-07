# packet_spot_market_price

[back](../packet.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    packet = ">= 3.2.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "packet_spot_market_price" {
  source = "./modules/packet/d/packet_spot_market_price"

  # facility - (required) is a type of string
  facility = null
  # plan - (required) is a type of string
  plan = null
}
```

[top](#index)

### Variables

```terraform
variable "facility" {
  description = "(required)"
  type        = string
}

variable "plan" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "packet_spot_market_price" "this" {
  # facility - (required) is a type of string
  facility = var.facility
  # plan - (required) is a type of string
  plan = var.plan
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.packet_spot_market_price.this.id
}

output "price" {
  description = "returns a number"
  value       = data.packet_spot_market_price.this.price
}

output "this" {
  value = packet_spot_market_price.this
}
```

[top](#index)