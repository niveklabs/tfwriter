# aws_kms_secrets

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_kms_secrets" {
  source = "./modules/aws/d/aws_kms_secrets"


  secret = [{
    context      = {}
    grant_tokens = []
    name         = null
    payload      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "secret" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      context      = map(string)
      grant_tokens = list(string)
      name         = string
      payload      = string
    }
  ))
}
```

[top](#index)

### Datasource

```terraform
data "aws_kms_secrets" "this" {

  dynamic "secret" {
    for_each = var.secret
    content {
      # context - (optional) is a type of map of string
      context = secret.value["context"]
      # grant_tokens - (optional) is a type of list of string
      grant_tokens = secret.value["grant_tokens"]
      # name - (required) is a type of string
      name = secret.value["name"]
      # payload - (required) is a type of string
      payload = secret.value["payload"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_kms_secrets.this.id
}

output "plaintext" {
  description = "returns a map of string"
  value       = data.aws_kms_secrets.this.plaintext
  sensitive   = true
}

output "this" {
  value = aws_kms_secrets.this
}
```

[top](#index)