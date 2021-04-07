# bigip_ltm_snatpool

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_snatpool" {
  source = "./modules/bigip/r/bigip_ltm_snatpool"

  # members - (required) is a type of set of string
  members = []
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "members" {
  description = "(required) - Specifies a translation address to add to or delete from a SNAT pool, at least one address is required."
  type        = set(string)
}

variable "name" {
  description = "(required) - SNAT Pool list Name, format /partition/name. e.g. /Common/snat_pool"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_snatpool" "this" {
  # members - (required) is a type of set of string
  members = var.members
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_ltm_snatpool.this.id
}

output "this" {
  value = bigip_ltm_snatpool.this
}
```

[top](#index)