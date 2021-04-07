# oci_core_instance_credentials

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_instance_credentials" {
  source = "./modules/oci/d/oci_core_instance_credentials"

  # instance_id - (required) is a type of string
  instance_id = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_instance_credentials" "this" {
  instance_id = var.instance_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_core_instance_credentials.this.id
}

output "password" {
  description = "returns a string"
  value       = data.oci_core_instance_credentials.this.password
}

output "username" {
  description = "returns a string"
  value       = data.oci_core_instance_credentials.this.username
}

output "this" {
  value = oci_core_instance_credentials.this
}
```

[top](#index)