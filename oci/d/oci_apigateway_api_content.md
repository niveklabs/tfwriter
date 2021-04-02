# oci_apigateway_api_content

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_apigateway_api_content" {
  source = "./modules/oci/d/oci_apigateway_api_content"

  # api_id - (required) is a type of string
  api_id = null
}
```

[top](#index)

### Variables

```terraform
variable "api_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_apigateway_api_content" "this" {
  api_id = var.api_id
}
```

[top](#index)

### Outputs

```terraform
output "content" {
  description = "returns a string"
  value       = data.oci_apigateway_api_content.this.content
}

output "id" {
  description = "returns a string"
  value       = data.oci_apigateway_api_content.this.id
}

output "this" {
  value = oci_apigateway_api_content.this
}
```

[top](#index)