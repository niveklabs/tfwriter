# akamai_dns_record_set

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_dns_record_set" {
  source = "./modules/akamai/d/akamai_dns_record_set"

  # host - (required) is a type of string
  host = null
  # record_type - (required) is a type of string
  record_type = null
  # zone - (required) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "host" {
  description = "(required)"
  type        = string
}

variable "record_type" {
  description = "(required)"
  type        = string
}

variable "zone" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "akamai_dns_record_set" "this" {
  host        = var.host
  record_type = var.record_type
  zone        = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_dns_record_set.this.id
}

output "rdata" {
  description = "returns a list of string"
  value       = data.akamai_dns_record_set.this.rdata
}

output "this" {
  value = akamai_dns_record_set.this
}
```

[top](#index)