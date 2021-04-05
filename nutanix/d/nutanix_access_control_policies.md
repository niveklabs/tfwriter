# nutanix_access_control_policies

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_access_control_policies" {
  source = "./modules/nutanix/d/nutanix_access_control_policies"


  metadata = [{
    filter         = null
    kind           = null
    length         = null
    offset         = null
    sort_attribute = null
    sort_order     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "metadata" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      filter         = string
      kind           = string
      length         = number
      offset         = number
      sort_attribute = string
      sort_order     = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "nutanix_access_control_policies" "this" {

  dynamic "metadata" {
    for_each = var.metadata
    content {
      filter         = metadata.value["filter"]
      kind           = metadata.value["kind"]
      length         = metadata.value["length"]
      offset         = metadata.value["offset"]
      sort_attribute = metadata.value["sort_attribute"]
      sort_order     = metadata.value["sort_order"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "api_version" {
  description = "returns a string"
  value       = data.nutanix_access_control_policies.this.api_version
}

output "entities" {
  description = "returns a list of object"
  value       = data.nutanix_access_control_policies.this.entities
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_access_control_policies.this.id
}

output "this" {
  value = nutanix_access_control_policies.this
}
```

[top](#index)