# aviatrix_caller_identity

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_caller_identity" {
  source = "./modules/aviatrix/d/aviatrix_caller_identity"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "aviatrix_caller_identity" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "cid" {
  description = "returns a string"
  value       = data.aviatrix_caller_identity.this.cid
}

output "id" {
  description = "returns a string"
  value       = data.aviatrix_caller_identity.this.id
}

output "this" {
  value = aviatrix_caller_identity.this
}
```

[top](#index)