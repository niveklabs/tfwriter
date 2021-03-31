# aws_partition

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_partition" {
  source = "./modules/aws/d/aws_partition"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "aws_partition" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "dns_suffix" {
  description = "returns a string"
  value       = data.aws_partition.this.dns_suffix
}

output "id" {
  description = "returns a string"
  value       = data.aws_partition.this.id
}

output "partition" {
  description = "returns a string"
  value       = data.aws_partition.this.partition
}

output "reverse_dns_prefix" {
  description = "returns a string"
  value       = data.aws_partition.this.reverse_dns_prefix
}

output "this" {
  value = aws_partition.this
}
```

[top](#index)