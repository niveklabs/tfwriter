# scaleway_lb_ip

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_lb_ip" {
  source = "./modules/scaleway/d/scaleway_lb_ip"

  # ip_address - (optional) is a type of string
  ip_address = null
  # ip_id - (optional) is a type of string
  ip_id = null
}
```

[top](#index)

### Variables

```terraform
variable "ip_address" {
  description = "(optional) - The IP address"
  type        = string
  default     = null
}

variable "ip_id" {
  description = "(optional) - The ID of the IP address"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "scaleway_lb_ip" "this" {
  # ip_address - (optional) is a type of string
  ip_address = var.ip_address
  # ip_id - (optional) is a type of string
  ip_id = var.ip_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.scaleway_lb_ip.this.id
}

output "lb_id" {
  description = "returns a string"
  value       = data.scaleway_lb_ip.this.lb_id
}

output "organization_id" {
  description = "returns a string"
  value       = data.scaleway_lb_ip.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = data.scaleway_lb_ip.this.project_id
}

output "region" {
  description = "returns a string"
  value       = data.scaleway_lb_ip.this.region
}

output "reverse" {
  description = "returns a string"
  value       = data.scaleway_lb_ip.this.reverse
}

output "this" {
  value = scaleway_lb_ip.this
}
```

[top](#index)