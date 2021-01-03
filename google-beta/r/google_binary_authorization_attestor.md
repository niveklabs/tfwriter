# google_binary_authorization_attestor

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
    google-beta = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_binary_authorization_attestor" {
  source = "./modules/google-beta/r/google_binary_authorization_attestor"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null

  attestation_authority_note = [{
    delegation_service_account_email = null
    note_reference                   = null
    public_keys = [{
      ascii_armored_pgp_public_key = null
      comment                      = null
      id                           = null
      pkix_public_key = [{
        public_key_pem      = null
        signature_algorithm = null
      }]
    }]
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
variable "description" {
  description = "(optional) - A descriptive comment. This field may be updated. The field may be\ndisplayed in chooser dialogs."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The resource name."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "attestation_authority_note" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      delegation_service_account_email = string
      note_reference                   = string
      public_keys = list(object(
        {
          ascii_armored_pgp_public_key = string
          comment                      = string
          id                           = string
          pkix_public_key = list(object(
            {
              public_key_pem      = string
              signature_algorithm = string
            }
          ))
        }
      ))
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
resource "google_binary_authorization_attestor" "this" {
  description = var.description
  name        = var.name
  project     = var.project

  dynamic "attestation_authority_note" {
    for_each = var.attestation_authority_note
    content {
      note_reference = attestation_authority_note.value["note_reference"]

      dynamic "public_keys" {
        for_each = attestation_authority_note.value.public_keys
        content {
          ascii_armored_pgp_public_key = public_keys.value["ascii_armored_pgp_public_key"]
          comment                      = public_keys.value["comment"]
          id                           = public_keys.value["id"]

          dynamic "pkix_public_key" {
            for_each = public_keys.value.pkix_public_key
            content {
              public_key_pem      = pkix_public_key.value["public_key_pem"]
              signature_algorithm = pkix_public_key.value["signature_algorithm"]
            }
          }

        }
      }

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
output "id" {
  description = "returns a string"
  value       = google_binary_authorization_attestor.this.id
}

output "project" {
  description = "returns a string"
  value       = google_binary_authorization_attestor.this.project
}

output "this" {
  value = google_binary_authorization_attestor.this
}
```

[top](#index)