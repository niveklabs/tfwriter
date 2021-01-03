# ovh_me_ipxe_scripts

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
module "ovh_me_ipxe_scripts" {
  source = "./modules/ovh/d/ovh_me_ipxe_scripts"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "ovh_me_ipxe_scripts" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.ovh_me_ipxe_scripts.this.id
}

output "result" {
  description = "returns a list of string"
  value       = data.ovh_me_ipxe_scripts.this.result
}

output "this" {
  value = ovh_me_ipxe_scripts.this
}
```

[top](#index)