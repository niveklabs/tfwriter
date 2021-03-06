# google_apigee_environment

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_apigee_environment" {
  source = "./modules/google/r/google_apigee_environment"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
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
variable "description" {
  description = "(optional) - Description of the environment."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - Display name of the environment."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The resource ID of the environment."
  type        = string
}

variable "org_id" {
  description = "(required) - The Apigee Organization associated with the Apigee environment,\nin the format 'organizations/{{org_name}}'."
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
resource "google_apigee_environment" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
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
  value       = google_apigee_environment.this.id
}

output "this" {
  value = google_apigee_environment.this
}
```

[top](#index)