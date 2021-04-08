# vultr_dns_domain

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vultr = ">= 2.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vultr_dns_domain" {
  source = "./modules/vultr/d/vultr_dns_domain"

  # domain - (required) is a type of string
  domain = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(required) - name of the domain"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vultr_dns_domain" "this" {
  # domain - (required) is a type of string
  domain = var.domain
}
```

[top](#index)

### Outputs

```terraform
output "date_created" {
  description = "returns a string"
  value       = data.vultr_dns_domain.this.date_created
}

output "id" {
  description = "returns a string"
  value       = data.vultr_dns_domain.this.id
}

output "this" {
  value = vultr_dns_domain.this
}
```

[top](#index)