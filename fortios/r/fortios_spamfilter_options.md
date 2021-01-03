# fortios_spamfilter_options

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_spamfilter_options" {
  source = "./modules/fortios/r/fortios_spamfilter_options"

  # dns_timeout - (optional) is a type of number
  dns_timeout = null
}
```

[top](#index)

### Variables

```terraform
variable "dns_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_spamfilter_options" "this" {
  dns_timeout = var.dns_timeout
}
```

[top](#index)

### Outputs

```terraform
output "dns_timeout" {
  description = "returns a number"
  value       = fortios_spamfilter_options.this.dns_timeout
}

output "id" {
  description = "returns a string"
  value       = fortios_spamfilter_options.this.id
}

output "this" {
  value = fortios_spamfilter_options.this
}
```

[top](#index)