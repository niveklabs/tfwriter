# oci_apigateway_api_validation

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_apigateway_api_validation" {
  source = "./modules/oci/d/oci_apigateway_api_validation"

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
data "oci_apigateway_api_validation" "this" {
  api_id = var.api_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_apigateway_api_validation.this.id
}

output "validations" {
  description = "returns a list of object"
  value       = data.oci_apigateway_api_validation.this.validations
}

output "this" {
  value = oci_apigateway_api_validation.this
}
```

[top](#index)