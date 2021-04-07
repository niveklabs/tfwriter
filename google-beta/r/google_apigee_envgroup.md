# google_apigee_envgroup

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_apigee_envgroup" {
  source = "./modules/google-beta/r/google_apigee_envgroup"

  # hostnames - (optional) is a type of list of string
  hostnames = []
  # name - (required) is a type of string
  name = null
  # org_id - (required) is a type of string
  org_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "hostnames" {
  description = "(optional) - Hostnames of the environment group."
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required) - The resource ID of the environment group."
  type        = string
}

variable "org_id" {
  description = "(required) - The Apigee Organization associated with the Apigee environment group,\nin the format 'organizations/{{org_name}}'."
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_apigee_envgroup" "this" {
  # hostnames - (optional) is a type of list of string
  hostnames = var.hostnames
  # name - (required) is a type of string
  name = var.name
  # org_id - (required) is a type of string
  org_id = var.org_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_apigee_envgroup.this.id
}

output "this" {
  value = google_apigee_envgroup.this
}
```

[top](#index)