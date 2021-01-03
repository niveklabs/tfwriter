# aviatrix_aws_tgw_peering

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_aws_tgw_peering" {
  source = "./modules/aviatrix/r/aviatrix_aws_tgw_peering"

  # tgw_name1 - (required) is a type of string
  tgw_name1 = null
  # tgw_name2 - (required) is a type of string
  tgw_name2 = null
}
```

[top](#index)

### Variables

```terraform
variable "tgw_name1" {
  description = "(required) - Name of the first AWS tgw to make a peer pair."
  type        = string
}

variable "tgw_name2" {
  description = "(required) - Name of the second AWS tgw to make a peer pair."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_aws_tgw_peering" "this" {
  tgw_name1 = var.tgw_name1
  tgw_name2 = var.tgw_name2
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_aws_tgw_peering.this.id
}

output "this" {
  value = aviatrix_aws_tgw_peering.this
}
```

[top](#index)