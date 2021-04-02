# azurerm_media_content_key_policy

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_media_content_key_policy" {
  source = "./modules/azurerm/r/azurerm_media_content_key_policy"

  # description - (optional) is a type of string
  description = null
  # media_services_account_name - (required) is a type of string
  media_services_account_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  policy_option = [{
    clear_key_configuration_enabled = null
    fairplay_configuration = [{
      ask = null
      offline_rental_configuration = [{
        playback_duration_seconds = null
        storage_duration_seconds  = null
      }]
      pfx                       = null
      pfx_password              = null
      rental_and_lease_key_type = null
      rental_duration_seconds   = null
    }]
    name                     = null
    open_restriction_enabled = null
    playready_configuration_license = [{
      allow_test_devices                       = null
      begin_date                               = null
      content_key_location_from_header_enabled = null
      content_key_location_from_key_id         = null
      content_type                             = null
      expiration_date                          = null
      grace_period                             = null
      license_type                             = null
      play_right = [{
        agc_and_color_stripe_restriction                         = null
        allow_passing_video_content_to_unknown_output            = null
        analog_video_opl                                         = null
        compressed_digital_audio_opl                             = null
        digital_video_only_content_restriction                   = null
        first_play_expiration                                    = null
        image_constraint_for_analog_component_video_restriction  = null
        image_constraint_for_analog_computer_monitor_restriction = null
        scms_restriction                                         = null
        uncompressed_digital_audio_opl                           = null
        uncompressed_digital_video_opl                           = null
      }]
      relative_begin_date      = null
      relative_expiration_date = null
    }]
    token_restriction = [{
      audience                           = null
      issuer                             = null
      open_id_connect_discovery_document = null
      primary_rsa_token_key_exponent     = null
      primary_rsa_token_key_modulus      = null
      primary_symmetric_token_key        = null
      primary_x509_token_key_raw         = null
      required_claim = [{
        type  = null
        value = null
      }]
      token_type = null
    }]
    widevine_configuration_template = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "media_services_account_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "policy_option" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      clear_key_configuration_enabled = bool
      fairplay_configuration = list(object(
        {
          ask = string
          offline_rental_configuration = list(object(
            {
              playback_duration_seconds = number
              storage_duration_seconds  = number
            }
          ))
          pfx                       = string
          pfx_password              = string
          rental_and_lease_key_type = string
          rental_duration_seconds   = number
        }
      ))
      name                     = string
      open_restriction_enabled = bool
      playready_configuration_license = list(object(
        {
          allow_test_devices                       = bool
          begin_date                               = string
          content_key_location_from_header_enabled = bool
          content_key_location_from_key_id         = string
          content_type                             = string
          expiration_date                          = string
          grace_period                             = string
          license_type                             = string
          play_right = list(object(
            {
              agc_and_color_stripe_restriction                         = number
              allow_passing_video_content_to_unknown_output            = string
              analog_video_opl                                         = number
              compressed_digital_audio_opl                             = number
              digital_video_only_content_restriction                   = bool
              first_play_expiration                                    = string
              image_constraint_for_analog_component_video_restriction  = bool
              image_constraint_for_analog_computer_monitor_restriction = bool
              scms_restriction                                         = number
              uncompressed_digital_audio_opl                           = number
              uncompressed_digital_video_opl                           = number
            }
          ))
          relative_begin_date      = string
          relative_expiration_date = string
        }
      ))
      token_restriction = list(object(
        {
          audience                           = string
          issuer                             = string
          open_id_connect_discovery_document = string
          primary_rsa_token_key_exponent     = string
          primary_rsa_token_key_modulus      = string
          primary_symmetric_token_key        = string
          primary_x509_token_key_raw         = string
          required_claim = list(object(
            {
              type  = string
              value = string
            }
          ))
          token_type = string
        }
      ))
      widevine_configuration_template = string
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_media_content_key_policy" "this" {
  description                 = var.description
  media_services_account_name = var.media_services_account_name
  name                        = var.name
  resource_group_name         = var.resource_group_name

  dynamic "policy_option" {
    for_each = var.policy_option
    content {
      clear_key_configuration_enabled = policy_option.value["clear_key_configuration_enabled"]
      name                            = policy_option.value["name"]
      open_restriction_enabled        = policy_option.value["open_restriction_enabled"]
      widevine_configuration_template = policy_option.value["widevine_configuration_template"]

      dynamic "fairplay_configuration" {
        for_each = policy_option.value.fairplay_configuration
        content {
          ask                       = fairplay_configuration.value["ask"]
          pfx                       = fairplay_configuration.value["pfx"]
          pfx_password              = fairplay_configuration.value["pfx_password"]
          rental_and_lease_key_type = fairplay_configuration.value["rental_and_lease_key_type"]
          rental_duration_seconds   = fairplay_configuration.value["rental_duration_seconds"]

          dynamic "offline_rental_configuration" {
            for_each = fairplay_configuration.value.offline_rental_configuration
            content {
              playback_duration_seconds = offline_rental_configuration.value["playback_duration_seconds"]
              storage_duration_seconds  = offline_rental_configuration.value["storage_duration_seconds"]
            }
          }

        }
      }

      dynamic "playready_configuration_license" {
        for_each = policy_option.value.playready_configuration_license
        content {
          allow_test_devices                       = playready_configuration_license.value["allow_test_devices"]
          begin_date                               = playready_configuration_license.value["begin_date"]
          content_key_location_from_header_enabled = playready_configuration_license.value["content_key_location_from_header_enabled"]
          content_key_location_from_key_id         = playready_configuration_license.value["content_key_location_from_key_id"]
          content_type                             = playready_configuration_license.value["content_type"]
          expiration_date                          = playready_configuration_license.value["expiration_date"]
          grace_period                             = playready_configuration_license.value["grace_period"]
          license_type                             = playready_configuration_license.value["license_type"]
          relative_begin_date                      = playready_configuration_license.value["relative_begin_date"]
          relative_expiration_date                 = playready_configuration_license.value["relative_expiration_date"]

          dynamic "play_right" {
            for_each = playready_configuration_license.value.play_right
            content {
              agc_and_color_stripe_restriction                         = play_right.value["agc_and_color_stripe_restriction"]
              allow_passing_video_content_to_unknown_output            = play_right.value["allow_passing_video_content_to_unknown_output"]
              analog_video_opl                                         = play_right.value["analog_video_opl"]
              compressed_digital_audio_opl                             = play_right.value["compressed_digital_audio_opl"]
              digital_video_only_content_restriction                   = play_right.value["digital_video_only_content_restriction"]
              first_play_expiration                                    = play_right.value["first_play_expiration"]
              image_constraint_for_analog_component_video_restriction  = play_right.value["image_constraint_for_analog_component_video_restriction"]
              image_constraint_for_analog_computer_monitor_restriction = play_right.value["image_constraint_for_analog_computer_monitor_restriction"]
              scms_restriction                                         = play_right.value["scms_restriction"]
              uncompressed_digital_audio_opl                           = play_right.value["uncompressed_digital_audio_opl"]
              uncompressed_digital_video_opl                           = play_right.value["uncompressed_digital_video_opl"]
            }
          }

        }
      }

      dynamic "token_restriction" {
        for_each = policy_option.value.token_restriction
        content {
          audience                           = token_restriction.value["audience"]
          issuer                             = token_restriction.value["issuer"]
          open_id_connect_discovery_document = token_restriction.value["open_id_connect_discovery_document"]
          primary_rsa_token_key_exponent     = token_restriction.value["primary_rsa_token_key_exponent"]
          primary_rsa_token_key_modulus      = token_restriction.value["primary_rsa_token_key_modulus"]
          primary_symmetric_token_key        = token_restriction.value["primary_symmetric_token_key"]
          primary_x509_token_key_raw         = token_restriction.value["primary_x509_token_key_raw"]
          token_type                         = token_restriction.value["token_type"]

          dynamic "required_claim" {
            for_each = token_restriction.value.required_claim
            content {
              type  = required_claim.value["type"]
              value = required_claim.value["value"]
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
      read   = timeouts.value["read"]
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
  value       = azurerm_media_content_key_policy.this.id
}

output "this" {
  value = azurerm_media_content_key_policy.this
}
```

[top](#index)