# signalfx_gcp_services

[back](../signalfx.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    signalfx = ">= 6.7.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "signalfx_gcp_services" {
  source = "./modules/signalfx/d/signalfx_gcp_services"


  services = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "services" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "signalfx_gcp_services" "this" {

  dynamic "services" {
    for_each = var.services
    content {
      # name - (required) is a type of string
      name = services.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.signalfx_gcp_services.this.id
}

output "this" {
  value = signalfx_gcp_services.this
}
```

[top](#index)