# dns_srv_record_set

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
    dns = ">= 3.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dns_srv_record_set" {
  source = "./modules/dns/d/dns_srv_record_set"

  # service - (required) is a type of string
  service = null
}
```

[top](#index)

### Variables

```terraform
variable "service" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "dns_srv_record_set" "this" {
  service = var.service
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.dns_srv_record_set.this.id
}

output "srv" {
  description = "returns a list of object"
  value       = data.dns_srv_record_set.this.srv
}

output "this" {
  value = dns_srv_record_set.this
}
```

[top](#index)