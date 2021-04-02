# bigip_ssl_certificate

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ssl_certificate" {
  source = "./modules/bigip/d/bigip_ssl_certificate"

  # name - (required) is a type of string
  name = null
  # partition - (required) is a type of string
  partition = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the certificate"
  type        = string
}

variable "partition" {
  description = "(required) - partition of resource group"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "bigip_ssl_certificate" "this" {
  name      = var.name
  partition = var.partition
}
```

[top](#index)

### Outputs

```terraform
output "certificate" {
  description = "returns a string"
  value       = data.bigip_ssl_certificate.this.certificate
}

output "id" {
  description = "returns a string"
  value       = data.bigip_ssl_certificate.this.id
}

output "this" {
  value = bigip_ssl_certificate.this
}
```

[top](#index)