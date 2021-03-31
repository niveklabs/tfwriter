# oci_marketplace_publication

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_marketplace_publication" {
  source = "./modules/oci/r/oci_marketplace_publication"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_agreement_acknowledged - (required) is a type of bool
  is_agreement_acknowledged = null
  # listing_type - (required) is a type of string
  listing_type = null
  # long_description - (optional) is a type of string
  long_description = null
  # name - (required) is a type of string
  name = null
  # short_description - (required) is a type of string
  short_description = null

  package_details = [{
    eula = [{
      eula_type    = null
      license_text = null
    }]
    image_id = null
    operating_system = [{
      name = null
    }]
    package_type    = null
    package_version = null
  }]

  support_contacts = [{
    email   = null
    name    = null
    phone   = null
    subject = null
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

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "is_agreement_acknowledged" {
  description = "(required)"
  type        = bool
}

variable "listing_type" {
  description = "(required)"
  type        = string
}

variable "long_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "short_description" {
  description = "(required)"
  type        = string
}

variable "package_details" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      eula = set(object(
        {
          eula_type    = string
          license_text = string
        }
      ))
      image_id = string
      operating_system = list(object(
        {
          name = string
        }
      ))
      package_type    = string
      package_version = string
    }
  ))
}

variable "support_contacts" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      email   = string
      name    = string
      phone   = string
      subject = string
    }
  ))
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
resource "oci_marketplace_publication" "this" {
  compartment_id            = var.compartment_id
  defined_tags              = var.defined_tags
  freeform_tags             = var.freeform_tags
  is_agreement_acknowledged = var.is_agreement_acknowledged
  listing_type              = var.listing_type
  long_description          = var.long_description
  name                      = var.name
  short_description         = var.short_description

  dynamic "package_details" {
    for_each = var.package_details
    content {
      image_id        = package_details.value["image_id"]
      package_type    = package_details.value["package_type"]
      package_version = package_details.value["package_version"]

      dynamic "eula" {
        for_each = package_details.value.eula
        content {
          eula_type    = eula.value["eula_type"]
          license_text = eula.value["license_text"]
        }
      }

      dynamic "operating_system" {
        for_each = package_details.value.operating_system
        content {
          name = operating_system.value["name"]
        }
      }

    }
  }

  dynamic "support_contacts" {
    for_each = var.support_contacts
    content {
      email   = support_contacts.value["email"]
      name    = support_contacts.value["name"]
      phone   = support_contacts.value["phone"]
      subject = support_contacts.value["subject"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_marketplace_publication.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_marketplace_publication.this.freeform_tags
}

output "icon" {
  description = "returns a list of object"
  value       = oci_marketplace_publication.this.icon
}

output "id" {
  description = "returns a string"
  value       = oci_marketplace_publication.this.id
}

output "long_description" {
  description = "returns a string"
  value       = oci_marketplace_publication.this.long_description
}

output "package_type" {
  description = "returns a string"
  value       = oci_marketplace_publication.this.package_type
}

output "state" {
  description = "returns a string"
  value       = oci_marketplace_publication.this.state
}

output "supported_operating_systems" {
  description = "returns a list of object"
  value       = oci_marketplace_publication.this.supported_operating_systems
}

output "time_created" {
  description = "returns a string"
  value       = oci_marketplace_publication.this.time_created
}

output "this" {
  value = oci_marketplace_publication.this
}
```

[top](#index)