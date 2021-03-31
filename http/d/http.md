# http

[back](../http.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    http = ">= 2.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "http" {
  source = "./modules/http/d/http"

  # request_headers - (optional) is a type of map of string
  request_headers = {}
  # url - (required) is a type of string
  url = null
}
```

[top](#index)

### Variables

```terraform
variable "request_headers" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "url" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "http" "this" {
  request_headers = var.request_headers
  url             = var.url
}
```

[top](#index)

### Outputs

```terraform
output "body" {
  description = "returns a string"
  value       = data.http.this.body
}

output "id" {
  description = "returns a string"
  value       = data.http.this.id
}

output "response_headers" {
  description = "returns a map of string"
  value       = data.http.this.response_headers
}

output "this" {
  value = http.this
}
```

[top](#index)