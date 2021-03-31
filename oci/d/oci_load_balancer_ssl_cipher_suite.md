# oci_load_balancer_ssl_cipher_suite

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_load_balancer_ssl_cipher_suite" {
  source = "./modules/oci/d/oci_load_balancer_ssl_cipher_suite"

  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_load_balancer_ssl_cipher_suite" "this" {
  load_balancer_id = var.load_balancer_id
  name             = var.name
}
```

[top](#index)

### Outputs

```terraform
output "ciphers" {
  description = "returns a list of string"
  value       = data.oci_load_balancer_ssl_cipher_suite.this.ciphers
}

output "id" {
  description = "returns a string"
  value       = data.oci_load_balancer_ssl_cipher_suite.this.id
}

output "state" {
  description = "returns a string"
  value       = data.oci_load_balancer_ssl_cipher_suite.this.state
}

output "this" {
  value = oci_load_balancer_ssl_cipher_suite.this
}
```

[top](#index)