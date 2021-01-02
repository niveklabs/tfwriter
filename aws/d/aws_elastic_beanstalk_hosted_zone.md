# aws_elastic_beanstalk_hosted_zone

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_elastic_beanstalk_hosted_zone" {
  source = "./modules/aws/d/aws_elastic_beanstalk_hosted_zone"

  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_elastic_beanstalk_hosted_zone" "this" {
  region = var.region
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_elastic_beanstalk_hosted_zone.this.id
}

output "this" {
  value = aws_elastic_beanstalk_hosted_zone.this
}
```

[top](#index)