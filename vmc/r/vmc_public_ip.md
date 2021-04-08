# vmc_public_ip

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
module "vmc_public_ip" {
  source = "./modules/vmc/r/vmc_public_ip"

  # display_name - (optional) is a type of string
  display_name = null
  # nsxt_reverse_proxy_url - (required) is a type of string
  nsxt_reverse_proxy_url = null
}
```

[top](#index)

### Variables

```terraform
variable "display_name" {
  description = "(optional) - Display name/notes about this resource"
  type        = string
  default     = null
}

variable "nsxt_reverse_proxy_url" {
  description = "(required) - NSX API public endpoint url used for public IP resource management"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vmc_public_ip" "this" {
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # nsxt_reverse_proxy_url - (required) is a type of string
  nsxt_reverse_proxy_url = var.nsxt_reverse_proxy_url
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vmc_public_ip.this.id
}

output "ip" {
  description = "returns a string"
  value       = vmc_public_ip.this.ip
}

output "this" {
  value = vmc_public_ip.this
}
```

[top](#index)