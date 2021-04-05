# google_apigee_instance_attachment

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
module "google_apigee_instance_attachment" {
  source = "./modules/google/r/google_apigee_instance_attachment"

  # environment - (required) is a type of string
  environment = null
  # instance_id - (required) is a type of string
  instance_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "environment" {
  description = "(required) - The resource ID of the environment."
  type        = string
}

variable "instance_id" {
  description = "(required) - The Apigee instance associated with the Apigee environment,\nin the format 'organisations/{{org_name}}/instances/{{instance_name}}'."
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_apigee_instance_attachment" "this" {
  environment = var.environment
  instance_id = var.instance_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_apigee_instance_attachment.this.id
}

output "name" {
  description = "returns a string"
  value       = google_apigee_instance_attachment.this.name
}

output "this" {
  value = google_apigee_instance_attachment.this
}
```

[top](#index)