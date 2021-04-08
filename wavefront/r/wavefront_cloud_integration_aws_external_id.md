# wavefront_cloud_integration_aws_external_id

[back](../wavefront.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    wavefront = ">= 2.8.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "wavefront_cloud_integration_aws_external_id" {
  source = "./modules/wavefront/r/wavefront_cloud_integration_aws_external_id"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Resource

```terraform
resource "wavefront_cloud_integration_aws_external_id" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = wavefront_cloud_integration_aws_external_id.this.id
}

output "this" {
  value = wavefront_cloud_integration_aws_external_id.this
}
```

[top](#index)