# fortios_webfilter_ipsurlfiltersetting6

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
module "fortios_webfilter_ipsurlfiltersetting6" {
  source = "./modules/fortios/r/fortios_webfilter_ipsurlfiltersetting6"

  # device - (optional) is a type of string
  device = null
  # distance - (optional) is a type of number
  distance = null
  # gateway6 - (optional) is a type of string
  gateway6 = null
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

variable "gateway6" {
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
resource "fortios_webfilter_ipsurlfiltersetting6" "this" {
  device     = var.device
  distance   = var.distance
  gateway6   = var.gateway6
  geo_filter = var.geo_filter
}
```

[top](#index)

### Outputs

```terraform
output "device" {
  description = "returns a string"
  value       = fortios_webfilter_ipsurlfiltersetting6.this.device
}

output "distance" {
  description = "returns a number"
  value       = fortios_webfilter_ipsurlfiltersetting6.this.distance
}

output "gateway6" {
  description = "returns a string"
  value       = fortios_webfilter_ipsurlfiltersetting6.this.gateway6
}

output "id" {
  description = "returns a string"
  value       = fortios_webfilter_ipsurlfiltersetting6.this.id
}

output "this" {
  value = fortios_webfilter_ipsurlfiltersetting6.this
}
```

[top](#index)