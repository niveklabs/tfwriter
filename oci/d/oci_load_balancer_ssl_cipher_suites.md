# oci_load_balancer_ssl_cipher_suites

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_load_balancer_ssl_cipher_suites" {
  source = "./modules/oci/d/oci_load_balancer_ssl_cipher_suites"

  # load_balancer_id - (optional) is a type of string
  load_balancer_id = null

  filter = [{
    name   = null
    regex  = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "load_balancer_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      regex  = bool
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "oci_load_balancer_ssl_cipher_suites" "this" {
  load_balancer_id = var.load_balancer_id

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      regex  = filter.value["regex"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_load_balancer_ssl_cipher_suites.this.id
}

output "ssl_cipher_suites" {
  description = "returns a list of object"
  value       = data.oci_load_balancer_ssl_cipher_suites.this.ssl_cipher_suites
}

output "this" {
  value = oci_load_balancer_ssl_cipher_suites.this
}
```

[top](#index)