# nsxt_provider_info

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_provider_info" {
  source = "./modules/nsxt/d/nsxt_provider_info"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "nsxt_provider_info" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "commit" {
  description = "returns a string"
  value       = data.nsxt_provider_info.this.commit
}

output "date" {
  description = "returns a string"
  value       = data.nsxt_provider_info.this.date
}

output "id" {
  description = "returns a string"
  value       = data.nsxt_provider_info.this.id
}

output "this" {
  value = nsxt_provider_info.this
}
```

[top](#index)