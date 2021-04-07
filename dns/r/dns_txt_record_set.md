# dns_txt_record_set

[back](../dns.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dns = ">= 3.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dns_txt_record_set" {
  source = "./modules/dns/r/dns_txt_record_set"

  # name - (optional) is a type of string
  name = null
  # ttl - (optional) is a type of number
  ttl = null
  # txt - (required) is a type of set of string
  txt = []
  # zone - (required) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "txt" {
  description = "(required)"
  type        = set(string)
}

variable "zone" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "dns_txt_record_set" "this" {
  # name - (optional) is a type of string
  name = var.name
  # ttl - (optional) is a type of number
  ttl = var.ttl
  # txt - (required) is a type of set of string
  txt = var.txt
  # zone - (required) is a type of string
  zone = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = dns_txt_record_set.this.id
}

output "this" {
  value = dns_txt_record_set.this
}
```

[top](#index)