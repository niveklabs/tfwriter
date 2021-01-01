# aws_kms_secrets
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
```hcl
variable "secret" {
  description = "nested mode: NestingSet, min items: 1, max items: 0"
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
```hcl
data "aws_kms_secrets" "this" {

  dynamic "secret" {
    for_each = var.secret
    content {
      context      = secret.value["context"]
      grant_tokens = secret.value["grant_tokens"]
      name         = secret.value["name"]
      payload      = secret.value["payload"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
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
