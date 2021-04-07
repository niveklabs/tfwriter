# fortios_voip_profile

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_voip_profile" {
  source = "./modules/fortios/r/fortios_voip_profile"

  # comment - (optional) is a type of string
  comment = null
  # name - (required) is a type of string
  name = null

  sccp = [{
    block_mcast      = null
    log_call_summary = null
    log_violations   = null
    max_calls        = null
    status           = null
    verify_header    = null
  }]

  sip = [{
    ack_rate                             = null
    block_ack                            = null
    block_bye                            = null
    block_cancel                         = null
    block_geo_red_options                = null
    block_info                           = null
    block_invite                         = null
    block_long_lines                     = null
    block_message                        = null
    block_notify                         = null
    block_options                        = null
    block_prack                          = null
    block_publish                        = null
    block_refer                          = null
    block_register                       = null
    block_subscribe                      = null
    block_unknown                        = null
    block_update                         = null
    bye_rate                             = null
    call_keepalive                       = null
    cancel_rate                          = null
    contact_fixup                        = null
    hnt_restrict_source_ip               = null
    hosted_nat_traversal                 = null
    info_rate                            = null
    invite_rate                          = null
    ips_rtp                              = null
    log_call_summary                     = null
    log_violations                       = null
    malformed_header_allow               = null
    malformed_header_call_id             = null
    malformed_header_contact             = null
    malformed_header_content_length      = null
    malformed_header_content_type        = null
    malformed_header_cseq                = null
    malformed_header_expires             = null
    malformed_header_from                = null
    malformed_header_max_forwards        = null
    malformed_header_p_asserted_identity = null
    malformed_header_rack                = null
    malformed_header_record_route        = null
    malformed_header_route               = null
    malformed_header_rseq                = null
    malformed_header_sdp_a               = null
    malformed_header_sdp_b               = null
    malformed_header_sdp_c               = null
    malformed_header_sdp_i               = null
    malformed_header_sdp_k               = null
    malformed_header_sdp_m               = null
    malformed_header_sdp_o               = null
    malformed_header_sdp_r               = null
    malformed_header_sdp_s               = null
    malformed_header_sdp_t               = null
    malformed_header_sdp_v               = null
    malformed_header_sdp_z               = null
    malformed_header_to                  = null
    malformed_header_via                 = null
    malformed_request_line               = null
    max_body_length                      = null
    max_dialogs                          = null
    max_idle_dialogs                     = null
    max_line_length                      = null
    message_rate                         = null
    nat_port_range                       = null
    nat_trace                            = null
    no_sdp_fixup                         = null
    notify_rate                          = null
    open_contact_pinhole                 = null
    open_record_route_pinhole            = null
    open_register_pinhole                = null
    open_via_pinhole                     = null
    options_rate                         = null
    prack_rate                           = null
    preserve_override                    = null
    provisional_invite_expiry_time       = null
    publish_rate                         = null
    refer_rate                           = null
    register_contact_trace               = null
    register_rate                        = null
    rfc2543_branch                       = null
    rtp                                  = null
    ssl_algorithm                        = null
    ssl_auth_client                      = null
    ssl_auth_server                      = null
    ssl_client_certificate               = null
    ssl_client_renegotiation             = null
    ssl_max_version                      = null
    ssl_min_version                      = null
    ssl_mode                             = null
    ssl_pfs                              = null
    ssl_send_empty_frags                 = null
    ssl_server_certificate               = null
    status                               = null
    strict_register                      = null
    subscribe_rate                       = null
    unknown_header                       = null
    update_rate                          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "sccp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      block_mcast      = string
      log_call_summary = string
      log_violations   = string
      max_calls        = number
      status           = string
      verify_header    = string
    }
  ))
  default = []
}

variable "sip" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ack_rate                             = number
      block_ack                            = string
      block_bye                            = string
      block_cancel                         = string
      block_geo_red_options                = string
      block_info                           = string
      block_invite                         = string
      block_long_lines                     = string
      block_message                        = string
      block_notify                         = string
      block_options                        = string
      block_prack                          = string
      block_publish                        = string
      block_refer                          = string
      block_register                       = string
      block_subscribe                      = string
      block_unknown                        = string
      block_update                         = string
      bye_rate                             = number
      call_keepalive                       = number
      cancel_rate                          = number
      contact_fixup                        = string
      hnt_restrict_source_ip               = string
      hosted_nat_traversal                 = string
      info_rate                            = number
      invite_rate                          = number
      ips_rtp                              = string
      log_call_summary                     = string
      log_violations                       = string
      malformed_header_allow               = string
      malformed_header_call_id             = string
      malformed_header_contact             = string
      malformed_header_content_length      = string
      malformed_header_content_type        = string
      malformed_header_cseq                = string
      malformed_header_expires             = string
      malformed_header_from                = string
      malformed_header_max_forwards        = string
      malformed_header_p_asserted_identity = string
      malformed_header_rack                = string
      malformed_header_record_route        = string
      malformed_header_route               = string
      malformed_header_rseq                = string
      malformed_header_sdp_a               = string
      malformed_header_sdp_b               = string
      malformed_header_sdp_c               = string
      malformed_header_sdp_i               = string
      malformed_header_sdp_k               = string
      malformed_header_sdp_m               = string
      malformed_header_sdp_o               = string
      malformed_header_sdp_r               = string
      malformed_header_sdp_s               = string
      malformed_header_sdp_t               = string
      malformed_header_sdp_v               = string
      malformed_header_sdp_z               = string
      malformed_header_to                  = string
      malformed_header_via                 = string
      malformed_request_line               = string
      max_body_length                      = number
      max_dialogs                          = number
      max_idle_dialogs                     = number
      max_line_length                      = number
      message_rate                         = number
      nat_port_range                       = string
      nat_trace                            = string
      no_sdp_fixup                         = string
      notify_rate                          = number
      open_contact_pinhole                 = string
      open_record_route_pinhole            = string
      open_register_pinhole                = string
      open_via_pinhole                     = string
      options_rate                         = number
      prack_rate                           = number
      preserve_override                    = string
      provisional_invite_expiry_time       = number
      publish_rate                         = number
      refer_rate                           = number
      register_contact_trace               = string
      register_rate                        = number
      rfc2543_branch                       = string
      rtp                                  = string
      ssl_algorithm                        = string
      ssl_auth_client                      = string
      ssl_auth_server                      = string
      ssl_client_certificate               = string
      ssl_client_renegotiation             = string
      ssl_max_version                      = string
      ssl_min_version                      = string
      ssl_mode                             = string
      ssl_pfs                              = string
      ssl_send_empty_frags                 = string
      ssl_server_certificate               = string
      status                               = string
      strict_register                      = string
      subscribe_rate                       = number
      unknown_header                       = string
      update_rate                          = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_voip_profile" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # name - (required) is a type of string
  name = var.name

  dynamic "sccp" {
    for_each = var.sccp
    content {
      # block_mcast - (optional) is a type of string
      block_mcast = sccp.value["block_mcast"]
      # log_call_summary - (optional) is a type of string
      log_call_summary = sccp.value["log_call_summary"]
      # log_violations - (optional) is a type of string
      log_violations = sccp.value["log_violations"]
      # max_calls - (optional) is a type of number
      max_calls = sccp.value["max_calls"]
      # status - (optional) is a type of string
      status = sccp.value["status"]
      # verify_header - (optional) is a type of string
      verify_header = sccp.value["verify_header"]
    }
  }

  dynamic "sip" {
    for_each = var.sip
    content {
      # ack_rate - (optional) is a type of number
      ack_rate = sip.value["ack_rate"]
      # block_ack - (optional) is a type of string
      block_ack = sip.value["block_ack"]
      # block_bye - (optional) is a type of string
      block_bye = sip.value["block_bye"]
      # block_cancel - (optional) is a type of string
      block_cancel = sip.value["block_cancel"]
      # block_geo_red_options - (optional) is a type of string
      block_geo_red_options = sip.value["block_geo_red_options"]
      # block_info - (optional) is a type of string
      block_info = sip.value["block_info"]
      # block_invite - (optional) is a type of string
      block_invite = sip.value["block_invite"]
      # block_long_lines - (optional) is a type of string
      block_long_lines = sip.value["block_long_lines"]
      # block_message - (optional) is a type of string
      block_message = sip.value["block_message"]
      # block_notify - (optional) is a type of string
      block_notify = sip.value["block_notify"]
      # block_options - (optional) is a type of string
      block_options = sip.value["block_options"]
      # block_prack - (optional) is a type of string
      block_prack = sip.value["block_prack"]
      # block_publish - (optional) is a type of string
      block_publish = sip.value["block_publish"]
      # block_refer - (optional) is a type of string
      block_refer = sip.value["block_refer"]
      # block_register - (optional) is a type of string
      block_register = sip.value["block_register"]
      # block_subscribe - (optional) is a type of string
      block_subscribe = sip.value["block_subscribe"]
      # block_unknown - (optional) is a type of string
      block_unknown = sip.value["block_unknown"]
      # block_update - (optional) is a type of string
      block_update = sip.value["block_update"]
      # bye_rate - (optional) is a type of number
      bye_rate = sip.value["bye_rate"]
      # call_keepalive - (optional) is a type of number
      call_keepalive = sip.value["call_keepalive"]
      # cancel_rate - (optional) is a type of number
      cancel_rate = sip.value["cancel_rate"]
      # contact_fixup - (optional) is a type of string
      contact_fixup = sip.value["contact_fixup"]
      # hnt_restrict_source_ip - (optional) is a type of string
      hnt_restrict_source_ip = sip.value["hnt_restrict_source_ip"]
      # hosted_nat_traversal - (optional) is a type of string
      hosted_nat_traversal = sip.value["hosted_nat_traversal"]
      # info_rate - (optional) is a type of number
      info_rate = sip.value["info_rate"]
      # invite_rate - (optional) is a type of number
      invite_rate = sip.value["invite_rate"]
      # ips_rtp - (optional) is a type of string
      ips_rtp = sip.value["ips_rtp"]
      # log_call_summary - (optional) is a type of string
      log_call_summary = sip.value["log_call_summary"]
      # log_violations - (optional) is a type of string
      log_violations = sip.value["log_violations"]
      # malformed_header_allow - (optional) is a type of string
      malformed_header_allow = sip.value["malformed_header_allow"]
      # malformed_header_call_id - (optional) is a type of string
      malformed_header_call_id = sip.value["malformed_header_call_id"]
      # malformed_header_contact - (optional) is a type of string
      malformed_header_contact = sip.value["malformed_header_contact"]
      # malformed_header_content_length - (optional) is a type of string
      malformed_header_content_length = sip.value["malformed_header_content_length"]
      # malformed_header_content_type - (optional) is a type of string
      malformed_header_content_type = sip.value["malformed_header_content_type"]
      # malformed_header_cseq - (optional) is a type of string
      malformed_header_cseq = sip.value["malformed_header_cseq"]
      # malformed_header_expires - (optional) is a type of string
      malformed_header_expires = sip.value["malformed_header_expires"]
      # malformed_header_from - (optional) is a type of string
      malformed_header_from = sip.value["malformed_header_from"]
      # malformed_header_max_forwards - (optional) is a type of string
      malformed_header_max_forwards = sip.value["malformed_header_max_forwards"]
      # malformed_header_p_asserted_identity - (optional) is a type of string
      malformed_header_p_asserted_identity = sip.value["malformed_header_p_asserted_identity"]
      # malformed_header_rack - (optional) is a type of string
      malformed_header_rack = sip.value["malformed_header_rack"]
      # malformed_header_record_route - (optional) is a type of string
      malformed_header_record_route = sip.value["malformed_header_record_route"]
      # malformed_header_route - (optional) is a type of string
      malformed_header_route = sip.value["malformed_header_route"]
      # malformed_header_rseq - (optional) is a type of string
      malformed_header_rseq = sip.value["malformed_header_rseq"]
      # malformed_header_sdp_a - (optional) is a type of string
      malformed_header_sdp_a = sip.value["malformed_header_sdp_a"]
      # malformed_header_sdp_b - (optional) is a type of string
      malformed_header_sdp_b = sip.value["malformed_header_sdp_b"]
      # malformed_header_sdp_c - (optional) is a type of string
      malformed_header_sdp_c = sip.value["malformed_header_sdp_c"]
      # malformed_header_sdp_i - (optional) is a type of string
      malformed_header_sdp_i = sip.value["malformed_header_sdp_i"]
      # malformed_header_sdp_k - (optional) is a type of string
      malformed_header_sdp_k = sip.value["malformed_header_sdp_k"]
      # malformed_header_sdp_m - (optional) is a type of string
      malformed_header_sdp_m = sip.value["malformed_header_sdp_m"]
      # malformed_header_sdp_o - (optional) is a type of string
      malformed_header_sdp_o = sip.value["malformed_header_sdp_o"]
      # malformed_header_sdp_r - (optional) is a type of string
      malformed_header_sdp_r = sip.value["malformed_header_sdp_r"]
      # malformed_header_sdp_s - (optional) is a type of string
      malformed_header_sdp_s = sip.value["malformed_header_sdp_s"]
      # malformed_header_sdp_t - (optional) is a type of string
      malformed_header_sdp_t = sip.value["malformed_header_sdp_t"]
      # malformed_header_sdp_v - (optional) is a type of string
      malformed_header_sdp_v = sip.value["malformed_header_sdp_v"]
      # malformed_header_sdp_z - (optional) is a type of string
      malformed_header_sdp_z = sip.value["malformed_header_sdp_z"]
      # malformed_header_to - (optional) is a type of string
      malformed_header_to = sip.value["malformed_header_to"]
      # malformed_header_via - (optional) is a type of string
      malformed_header_via = sip.value["malformed_header_via"]
      # malformed_request_line - (optional) is a type of string
      malformed_request_line = sip.value["malformed_request_line"]
      # max_body_length - (optional) is a type of number
      max_body_length = sip.value["max_body_length"]
      # max_dialogs - (optional) is a type of number
      max_dialogs = sip.value["max_dialogs"]
      # max_idle_dialogs - (optional) is a type of number
      max_idle_dialogs = sip.value["max_idle_dialogs"]
      # max_line_length - (optional) is a type of number
      max_line_length = sip.value["max_line_length"]
      # message_rate - (optional) is a type of number
      message_rate = sip.value["message_rate"]
      # nat_port_range - (optional) is a type of string
      nat_port_range = sip.value["nat_port_range"]
      # nat_trace - (optional) is a type of string
      nat_trace = sip.value["nat_trace"]
      # no_sdp_fixup - (optional) is a type of string
      no_sdp_fixup = sip.value["no_sdp_fixup"]
      # notify_rate - (optional) is a type of number
      notify_rate = sip.value["notify_rate"]
      # open_contact_pinhole - (optional) is a type of string
      open_contact_pinhole = sip.value["open_contact_pinhole"]
      # open_record_route_pinhole - (optional) is a type of string
      open_record_route_pinhole = sip.value["open_record_route_pinhole"]
      # open_register_pinhole - (optional) is a type of string
      open_register_pinhole = sip.value["open_register_pinhole"]
      # open_via_pinhole - (optional) is a type of string
      open_via_pinhole = sip.value["open_via_pinhole"]
      # options_rate - (optional) is a type of number
      options_rate = sip.value["options_rate"]
      # prack_rate - (optional) is a type of number
      prack_rate = sip.value["prack_rate"]
      # preserve_override - (optional) is a type of string
      preserve_override = sip.value["preserve_override"]
      # provisional_invite_expiry_time - (optional) is a type of number
      provisional_invite_expiry_time = sip.value["provisional_invite_expiry_time"]
      # publish_rate - (optional) is a type of number
      publish_rate = sip.value["publish_rate"]
      # refer_rate - (optional) is a type of number
      refer_rate = sip.value["refer_rate"]
      # register_contact_trace - (optional) is a type of string
      register_contact_trace = sip.value["register_contact_trace"]
      # register_rate - (optional) is a type of number
      register_rate = sip.value["register_rate"]
      # rfc2543_branch - (optional) is a type of string
      rfc2543_branch = sip.value["rfc2543_branch"]
      # rtp - (optional) is a type of string
      rtp = sip.value["rtp"]
      # ssl_algorithm - (optional) is a type of string
      ssl_algorithm = sip.value["ssl_algorithm"]
      # ssl_auth_client - (optional) is a type of string
      ssl_auth_client = sip.value["ssl_auth_client"]
      # ssl_auth_server - (optional) is a type of string
      ssl_auth_server = sip.value["ssl_auth_server"]
      # ssl_client_certificate - (optional) is a type of string
      ssl_client_certificate = sip.value["ssl_client_certificate"]
      # ssl_client_renegotiation - (optional) is a type of string
      ssl_client_renegotiation = sip.value["ssl_client_renegotiation"]
      # ssl_max_version - (optional) is a type of string
      ssl_max_version = sip.value["ssl_max_version"]
      # ssl_min_version - (optional) is a type of string
      ssl_min_version = sip.value["ssl_min_version"]
      # ssl_mode - (optional) is a type of string
      ssl_mode = sip.value["ssl_mode"]
      # ssl_pfs - (optional) is a type of string
      ssl_pfs = sip.value["ssl_pfs"]
      # ssl_send_empty_frags - (optional) is a type of string
      ssl_send_empty_frags = sip.value["ssl_send_empty_frags"]
      # ssl_server_certificate - (optional) is a type of string
      ssl_server_certificate = sip.value["ssl_server_certificate"]
      # status - (optional) is a type of string
      status = sip.value["status"]
      # strict_register - (optional) is a type of string
      strict_register = sip.value["strict_register"]
      # subscribe_rate - (optional) is a type of number
      subscribe_rate = sip.value["subscribe_rate"]
      # unknown_header - (optional) is a type of string
      unknown_header = sip.value["unknown_header"]
      # update_rate - (optional) is a type of number
      update_rate = sip.value["update_rate"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_voip_profile.this.id
}

output "this" {
  value = fortios_voip_profile.this
}
```

[top](#index)