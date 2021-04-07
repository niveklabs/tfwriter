# fortios_webfilter_ipsurlfiltercachesetting

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
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_webfilter_ipsurlfiltercachesetting" {
  source = "./modules/fortios/r/fortios_webfilter_ipsurlfiltercachesetting"

  # dns_retry_interval - (optional) is a type of number
  dns_retry_interval = null
  # extended_ttl - (optional) is a type of number
  extended_ttl = null
}
```

[top](#index)

### Variables

```terraform
variable "dns_retry_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "extended_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_webfilter_ipsurlfiltercachesetting" "this" {
  # dns_retry_interval - (optional) is a type of number
  dns_retry_interval = var.dns_retry_interval
  # extended_ttl - (optional) is a type of number
  extended_ttl = var.extended_ttl
}
```

[top](#index)

### Outputs

```terraform
output "dns_retry_interval" {
  description = "returns a number"
  value       = fortios_webfilter_ipsurlfiltercachesetting.this.dns_retry_interval
}

output "extended_ttl" {
  description = "returns a number"
  value       = fortios_webfilter_ipsurlfiltercachesetting.this.extended_ttl
}

output "id" {
  description = "returns a string"
  value       = fortios_webfilter_ipsurlfiltercachesetting.this.id
}

output "this" {
  value = fortios_webfilter_ipsurlfiltercachesetting.this
}
```

[top](#index)