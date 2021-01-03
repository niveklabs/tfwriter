# ovh_dedicated_servers

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
module "ovh_dedicated_servers" {
  source = "./modules/ovh/d/ovh_dedicated_servers"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "ovh_dedicated_servers" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.ovh_dedicated_servers.this.id
}

output "result" {
  description = "returns a list of string"
  value       = data.ovh_dedicated_servers.this.result
}

output "this" {
  value = ovh_dedicated_servers.this
}
```

[top](#index)