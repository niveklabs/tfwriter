# triton_datacenter

[back](../triton.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    triton = ">= 0.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "triton_datacenter" {
  source = "./modules/triton/d/triton_datacenter"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "triton_datacenter" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "endpoint" {
  description = "returns a string"
  value       = data.triton_datacenter.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = data.triton_datacenter.this.id
}

output "name" {
  description = "returns a string"
  value       = data.triton_datacenter.this.name
}

output "this" {
  value = triton_datacenter.this
}
```

[top](#index)