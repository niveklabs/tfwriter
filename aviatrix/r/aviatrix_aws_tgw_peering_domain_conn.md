# aviatrix_aws_tgw_peering_domain_conn

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
module "aviatrix_aws_tgw_peering_domain_conn" {
  source = "./modules/aviatrix/r/aviatrix_aws_tgw_peering_domain_conn"

  # domain_name1 - (required) is a type of string
  domain_name1 = null
  # domain_name2 - (required) is a type of string
  domain_name2 = null
  # tgw_name1 - (required) is a type of string
  tgw_name1 = null
  # tgw_name2 - (required) is a type of string
  tgw_name2 = null
}
```

[top](#index)

### Variables

```terraform
variable "domain_name1" {
  description = "(required) - The name of the source domain to make a connection."
  type        = string
}

variable "domain_name2" {
  description = "(required) - The name of the destination domain to make a connection."
  type        = string
}

variable "tgw_name1" {
  description = "(required) - The AWS tgw name of the source domain to make a connection."
  type        = string
}

variable "tgw_name2" {
  description = "(required) - The AWS tgw name of the destination domain to make a connection."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_aws_tgw_peering_domain_conn" "this" {
  domain_name1 = var.domain_name1
  domain_name2 = var.domain_name2
  tgw_name1    = var.tgw_name1
  tgw_name2    = var.tgw_name2
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_aws_tgw_peering_domain_conn.this.id
}

output "this" {
  value = aviatrix_aws_tgw_peering_domain_conn.this
}
```

[top](#index)