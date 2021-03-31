# ns1_record

[back](../ns1.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ns1 = ">= 1.9.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ns1_record" {
  source = "./modules/ns1/d/ns1_record"

  # domain - (required) is a type of string
  domain = null
  # type - (required) is a type of string
  type = null
  # zone - (required) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(required)"
  type        = string
}

variable "type" {
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
data "ns1_record" "this" {
  domain = var.domain
  type   = var.type
  zone   = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "answers" {
  description = "returns a list of object"
  value       = data.ns1_record.this.answers
}

output "filters" {
  description = "returns a list of object"
  value       = data.ns1_record.this.filters
}

output "id" {
  description = "returns a string"
  value       = data.ns1_record.this.id
}

output "link" {
  description = "returns a string"
  value       = data.ns1_record.this.link
}

output "meta" {
  description = "returns a map of string"
  value       = data.ns1_record.this.meta
}

output "regions" {
  description = "returns a list of object"
  value       = data.ns1_record.this.regions
}

output "short_answers" {
  description = "returns a list of string"
  value       = data.ns1_record.this.short_answers
}

output "ttl" {
  description = "returns a number"
  value       = data.ns1_record.this.ttl
}

output "use_client_subnet" {
  description = "returns a bool"
  value       = data.ns1_record.this.use_client_subnet
}

output "this" {
  value = ns1_record.this
}
```

[top](#index)