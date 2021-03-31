# fortios_webfilter_ipsurlfiltersetting

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
module "fortios_webfilter_ipsurlfiltersetting" {
  source = "./modules/fortios/r/fortios_webfilter_ipsurlfiltersetting"

  # device - (optional) is a type of string
  device = null
  # distance - (optional) is a type of number
  distance = null
  # gateway - (optional) is a type of string
  gateway = null
  # geo_filter - (optional) is a type of string
  geo_filter = null
}
```

[top](#index)

### Variables

```terraform
variable "device" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "distance" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "gateway" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "geo_filter" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_webfilter_ipsurlfiltersetting" "this" {
  device     = var.device
  distance   = var.distance
  gateway    = var.gateway
  geo_filter = var.geo_filter
}
```

[top](#index)

### Outputs

```terraform
output "device" {
  description = "returns a string"
  value       = fortios_webfilter_ipsurlfiltersetting.this.device
}

output "distance" {
  description = "returns a number"
  value       = fortios_webfilter_ipsurlfiltersetting.this.distance
}

output "gateway" {
  description = "returns a string"
  value       = fortios_webfilter_ipsurlfiltersetting.this.gateway
}

output "id" {
  description = "returns a string"
  value       = fortios_webfilter_ipsurlfiltersetting.this.id
}

output "this" {
  value = fortios_webfilter_ipsurlfiltersetting.this
}
```

[top](#index)