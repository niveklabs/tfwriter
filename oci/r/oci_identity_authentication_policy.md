# oci_identity_authentication_policy

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_identity_authentication_policy" {
  source = "./modules/oci/r/oci_identity_authentication_policy"

  # compartment_id - (required) is a type of string
  compartment_id = null

  network_policy = [{
    network_source_ids = []
  }]

  password_policy = [{
    is_lowercase_characters_required = null
    is_numeric_characters_required   = null
    is_special_characters_required   = null
    is_uppercase_characters_required = null
    is_username_containment_allowed  = null
    minimum_password_length          = null
  }]

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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "network_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      network_source_ids = list(string)
    }
  ))
  default = []
}

variable "password_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      is_lowercase_characters_required = bool
      is_numeric_characters_required   = bool
      is_special_characters_required   = bool
      is_uppercase_characters_required = bool
      is_username_containment_allowed  = bool
      minimum_password_length          = number
    }
  ))
  default = []
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
resource "oci_identity_authentication_policy" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id

  dynamic "network_policy" {
    for_each = var.network_policy
    content {
      # network_source_ids - (optional) is a type of list of string
      network_source_ids = network_policy.value["network_source_ids"]
    }
  }

  dynamic "password_policy" {
    for_each = var.password_policy
    content {
      # is_lowercase_characters_required - (optional) is a type of bool
      is_lowercase_characters_required = password_policy.value["is_lowercase_characters_required"]
      # is_numeric_characters_required - (optional) is a type of bool
      is_numeric_characters_required = password_policy.value["is_numeric_characters_required"]
      # is_special_characters_required - (optional) is a type of bool
      is_special_characters_required = password_policy.value["is_special_characters_required"]
      # is_uppercase_characters_required - (optional) is a type of bool
      is_uppercase_characters_required = password_policy.value["is_uppercase_characters_required"]
      # is_username_containment_allowed - (optional) is a type of bool
      is_username_containment_allowed = password_policy.value["is_username_containment_allowed"]
      # minimum_password_length - (optional) is a type of number
      minimum_password_length = password_policy.value["minimum_password_length"]
    }
  }

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
  value       = oci_identity_authentication_policy.this.id
}

output "this" {
  value = oci_identity_authentication_policy.this
}
```

[top](#index)