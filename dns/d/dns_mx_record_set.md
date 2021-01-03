# dns_mx_record_set

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
module "dns_mx_record_set" {
  source = "./modules/dns/d/dns_mx_record_set"

  # domain - (required) is a type of string
  domain = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "dns_mx_record_set" "this" {
  domain = var.domain
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.dns_mx_record_set.this.id
}

output "mx" {
  description = "returns a list of object"
  value       = data.dns_mx_record_set.this.mx
}

output "this" {
  value = dns_mx_record_set.this
}
```

[top](#index)