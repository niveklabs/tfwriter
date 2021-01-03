# dns_ptr_record_set

[back](../dns.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dns = ">= 3.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dns_ptr_record_set" {
  source = "./modules/dns/d/dns_ptr_record_set"

  # ip_address - (required) is a type of string
  ip_address = null
}
```

[top](#index)

### Variables

```terraform
variable "ip_address" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "dns_ptr_record_set" "this" {
  ip_address = var.ip_address
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.dns_ptr_record_set.this.id
}

output "ptr" {
  description = "returns a string"
  value       = data.dns_ptr_record_set.this.ptr
}

output "this" {
  value = dns_ptr_record_set.this
}
```

[top](#index)