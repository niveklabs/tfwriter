# hcloud_rdns

[back](../hcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcloud = ">= 1.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcloud_rdns" {
  source = "./modules/hcloud/r/hcloud_rdns"

  # dns_ptr - (required) is a type of string
  dns_ptr = null
  # floating_ip_id - (optional) is a type of number
  floating_ip_id = null
  # ip_address - (required) is a type of string
  ip_address = null
  # server_id - (optional) is a type of number
  server_id = null
}
```

[top](#index)

### Variables

```terraform
variable "dns_ptr" {
  description = "(required)"
  type        = string
}

variable "floating_ip_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ip_address" {
  description = "(required)"
  type        = string
}

variable "server_id" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "hcloud_rdns" "this" {
  dns_ptr        = var.dns_ptr
  floating_ip_id = var.floating_ip_id
  ip_address     = var.ip_address
  server_id      = var.server_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = hcloud_rdns.this.id
}

output "this" {
  value = hcloud_rdns.this
}
```

[top](#index)