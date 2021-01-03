# digitalocean_record

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    digitalocean = ">= 2.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_record" {
  source = "./modules/digitalocean/d/digitalocean_record"

  # domain - (required) is a type of string
  domain = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(required) - domain of the name record"
  type        = string
}

variable "name" {
  description = "(required) - name of the record"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_record" "this" {
  domain = var.domain
  name   = var.name
}
```

[top](#index)

### Outputs

```terraform
output "data" {
  description = "returns a string"
  value       = data.digitalocean_record.this.data
}

output "flags" {
  description = "returns a number"
  value       = data.digitalocean_record.this.flags
}

output "id" {
  description = "returns a string"
  value       = data.digitalocean_record.this.id
}

output "port" {
  description = "returns a number"
  value       = data.digitalocean_record.this.port
}

output "priority" {
  description = "returns a number"
  value       = data.digitalocean_record.this.priority
}

output "tag" {
  description = "returns a string"
  value       = data.digitalocean_record.this.tag
}

output "ttl" {
  description = "returns a number"
  value       = data.digitalocean_record.this.ttl
}

output "type" {
  description = "returns a string"
  value       = data.digitalocean_record.this.type
}

output "weight" {
  description = "returns a number"
  value       = data.digitalocean_record.this.weight
}

output "this" {
  value = digitalocean_record.this
}
```

[top](#index)