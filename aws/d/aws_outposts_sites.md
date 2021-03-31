# aws_outposts_sites

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
module "aws_outposts_sites" {
  source = "./modules/aws/d/aws_outposts_sites"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "aws_outposts_sites" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_outposts_sites.this.id
}

output "ids" {
  description = "returns a set of string"
  value       = data.aws_outposts_sites.this.ids
}

output "this" {
  value = aws_outposts_sites.this
}
```

[top](#index)