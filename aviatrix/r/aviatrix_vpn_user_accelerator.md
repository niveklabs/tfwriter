# aviatrix_vpn_user_accelerator

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
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_vpn_user_accelerator" {
  source = "./modules/aviatrix/r/aviatrix_vpn_user_accelerator"

  # elb_name - (required) is a type of string
  elb_name = null
}
```

[top](#index)

### Variables

```terraform
variable "elb_name" {
  description = "(required) - ELB to include into the VPN User Accelerator."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_vpn_user_accelerator" "this" {
  elb_name = var.elb_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_vpn_user_accelerator.this.id
}

output "this" {
  value = aviatrix_vpn_user_accelerator.this
}
```

[top](#index)