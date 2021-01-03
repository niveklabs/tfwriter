# ovh_me_ipxe_script

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.10.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_me_ipxe_script" {
  source = "./modules/ovh/d/ovh_me_ipxe_script"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of your script"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "ovh_me_ipxe_script" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.ovh_me_ipxe_script.this.id
}

output "script" {
  description = "returns a string"
  value       = data.ovh_me_ipxe_script.this.script
}

output "this" {
  value = ovh_me_ipxe_script.this
}
```

[top](#index)