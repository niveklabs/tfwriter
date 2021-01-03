# exoscale_compute_ipaddress

[back](../exoscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    exoscale = ">= 0.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_compute_ipaddress" {
  source = "./modules/exoscale/d/exoscale_compute_ipaddress"

  # description - (optional) is a type of string
  description = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zone - (required) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the Elastic IP"
  type        = string
  default     = null
}

variable "ip_address" {
  description = "(optional) - IP Address"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Map of tags (key: value)"
  type        = map(string)
  default     = null
}

variable "zone" {
  description = "(required) - Name of the zone"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "exoscale_compute_ipaddress" "this" {
  description = var.description
  ip_address  = var.ip_address
  tags        = var.tags
  zone        = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.exoscale_compute_ipaddress.this.id
}

output "this" {
  value = exoscale_compute_ipaddress.this
}
```

[top](#index)