# dns_txt_record_set

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
module "dns_txt_record_set" {
  source = "./modules/dns/d/dns_txt_record_set"

  # host - (required) is a type of string
  host = null
}
```

[top](#index)

### Variables

```terraform
variable "host" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "dns_txt_record_set" "this" {
  host = var.host
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.dns_txt_record_set.this.id
}

output "record" {
  description = "returns a string"
  value       = data.dns_txt_record_set.this.record
}

output "records" {
  description = "returns a list of string"
  value       = data.dns_txt_record_set.this.records
}

output "this" {
  value = dns_txt_record_set.this
}
```

[top](#index)