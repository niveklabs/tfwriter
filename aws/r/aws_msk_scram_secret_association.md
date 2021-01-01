# aws_msk_scram_secret_association

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_msk_scram_secret_association" {
  source = "./modules/aws/r/aws_msk_scram_secret_association"

  # cluster_arn - (required) is a type of string
  cluster_arn = null
  # secret_arn_list - (required) is a type of set of string
  secret_arn_list = []
}
```

[top](#index)

### Variables

```hcl
variable "cluster_arn" {
  description = "(required)"
  type        = string
}

variable "secret_arn_list" {
  description = "(required)"
  type        = set(string)
}
```

[top](#index)

### Resource

```hcl
resource "aws_msk_scram_secret_association" "this" {
  cluster_arn     = var.cluster_arn
  secret_arn_list = var.secret_arn_list
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_msk_scram_secret_association.this.id
}

output "this" {
  value = aws_msk_scram_secret_association.this
}
```

[top](#index)