# thunder_slb_template_client_ssl

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_slb_template_client_ssl" {
  source = "./modules/thunder/r/thunder_slb_template_client_ssl"

  # ad_group_list - (optional) is a type of string
  ad_group_list = null
  # alert_type - (optional) is a type of string
  alert_type = null
  # auth_sg - (optional) is a type of string
  auth_sg = null
  # auth_sg_dn - (optional) is a type of number
  auth_sg_dn = null
  # auth_sg_filter - (optional) is a type of string
  auth_sg_filter = null
  # auth_username - (optional) is a type of string
  auth_username = null
  # auth_username_attribute - (optional) is a type of string
  auth_username_attribute = null
  # authen_name - (optional) is a type of string
  authen_name = null
  # authorization - (optional) is a type of number
  authorization = null
  # bypass_cert_issuer_class_list_name - (optional) is a type of string
  bypass_cert_issuer_class_list_name = null
  # bypass_cert_san_class_list_name - (optional) is a type of string
  bypass_cert_san_class_list_name = null
  # bypass_cert_subject_class_list_name - (optional) is a type of string
  bypass_cert_subject_class_list_name = null
  # cache_persistence_list_name - (optional) is a type of string
  cache_persistence_list_name = null
  # case_insensitive - (optional) is a type of number
  case_insensitive = null
  # cert_alternate - (optional) is a type of string
  cert_alternate = null
  # cert_revoke_action - (optional) is a type of string
  cert_revoke_action = null
  # cert_shared_str - (optional) is a type of string
  cert_shared_str = null
  # cert_str - (optional) is a type of string
  cert_str = null
  # cert_unknown_action - (optional) is a type of string
  cert_unknown_action = null
  # chain_cert - (optional) is a type of string
  chain_cert = null
  # chain_cert_shared_str - (optional) is a type of string
  chain_cert_shared_str = null
  # class_list_name - (optional) is a type of string
  class_list_name = null
  # client_auth_case_insensitive - (optional) is a type of number
  client_auth_case_insensitive = null
  # client_auth_class_list - (optional) is a type of string
  client_auth_class_list = null
  # client_certificate - (optional) is a type of string
  client_certificate = null
  # close_notify - (optional) is a type of number
  close_notify = null
  # dgversion - (optional) is a type of number
  dgversion = null
  # dh_type - (optional) is a type of string
  dh_type = null
  # direct_client_server_auth - (optional) is a type of number
  direct_client_server_auth = null
  # disable_sslv3 - (optional) is a type of number
  disable_sslv3 = null
  # enable_tls_alert_logging - (optional) is a type of number
  enable_tls_alert_logging = null
  # exception_ad_group_list - (optional) is a type of string
  exception_ad_group_list = null
  # exception_certificate_issuer_cl_name - (optional) is a type of string
  exception_certificate_issuer_cl_name = null
  # exception_certificate_san_cl_name - (optional) is a type of string
  exception_certificate_san_cl_name = null
  # exception_certificate_subject_cl_name - (optional) is a type of string
  exception_certificate_subject_cl_name = null
  # exception_sni_cl_name - (optional) is a type of string
  exception_sni_cl_name = null
  # exception_user_name_list - (optional) is a type of string
  exception_user_name_list = null
  # expire_hours - (optional) is a type of number
  expire_hours = null
  # forward_encrypted - (optional) is a type of string
  forward_encrypted = null
  # forward_passphrase - (optional) is a type of string
  forward_passphrase = null
  # forward_proxy_alt_sign - (optional) is a type of number
  forward_proxy_alt_sign = null
  # forward_proxy_block_message - (optional) is a type of string
  forward_proxy_block_message = null
  # forward_proxy_ca_cert - (optional) is a type of string
  forward_proxy_ca_cert = null
  # forward_proxy_ca_key - (optional) is a type of string
  forward_proxy_ca_key = null
  # forward_proxy_cert_cache_limit - (optional) is a type of number
  forward_proxy_cert_cache_limit = null
  # forward_proxy_cert_cache_timeout - (optional) is a type of number
  forward_proxy_cert_cache_timeout = null
  # forward_proxy_cert_expiry - (optional) is a type of number
  forward_proxy_cert_expiry = null
  # forward_proxy_cert_not_ready_action - (optional) is a type of string
  forward_proxy_cert_not_ready_action = null
  # forward_proxy_cert_revoke_action - (optional) is a type of number
  forward_proxy_cert_revoke_action = null
  # forward_proxy_cert_unknown_action - (optional) is a type of number
  forward_proxy_cert_unknown_action = null
  # forward_proxy_crl_disable - (optional) is a type of number
  forward_proxy_crl_disable = null
  # forward_proxy_decrypted_dscp - (optional) is a type of number
  forward_proxy_decrypted_dscp = null
  # forward_proxy_decrypted_dscp_bypass - (optional) is a type of number
  forward_proxy_decrypted_dscp_bypass = null
  # forward_proxy_enable - (optional) is a type of number
  forward_proxy_enable = null
  # forward_proxy_failsafe_disable - (optional) is a type of number
  forward_proxy_failsafe_disable = null
  # forward_proxy_log_disable - (optional) is a type of number
  forward_proxy_log_disable = null
  # forward_proxy_no_shared_cipher_action - (optional) is a type of number
  forward_proxy_no_shared_cipher_action = null
  # forward_proxy_no_sni_action - (optional) is a type of string
  forward_proxy_no_sni_action = null
  # forward_proxy_ocsp_disable - (optional) is a type of number
  forward_proxy_ocsp_disable = null
  # forward_proxy_selfsign_redir - (optional) is a type of number
  forward_proxy_selfsign_redir = null
  # forward_proxy_ssl_version - (optional) is a type of number
  forward_proxy_ssl_version = null
  # forward_proxy_verify_cert_fail_action - (optional) is a type of number
  forward_proxy_verify_cert_fail_action = null
  # fp_alt_cert - (optional) is a type of string
  fp_alt_cert = null
  # fp_alt_encrypted - (optional) is a type of string
  fp_alt_encrypted = null
  # fp_alt_key - (optional) is a type of string
  fp_alt_key = null
  # fp_alt_passphrase - (optional) is a type of string
  fp_alt_passphrase = null
  # fp_cert_ext_aia_ca_issuers - (optional) is a type of string
  fp_cert_ext_aia_ca_issuers = null
  # fp_cert_ext_aia_ocsp - (optional) is a type of string
  fp_cert_ext_aia_ocsp = null
  # fp_cert_ext_crldp - (optional) is a type of string
  fp_cert_ext_crldp = null
  # fp_cert_fetch_autonat - (optional) is a type of string
  fp_cert_fetch_autonat = null
  # fp_cert_fetch_autonat_precedence - (optional) is a type of number
  fp_cert_fetch_autonat_precedence = null
  # fp_cert_fetch_natpool_name - (optional) is a type of string
  fp_cert_fetch_natpool_name = null
  # fp_cert_fetch_natpool_name_shared - (optional) is a type of string
  fp_cert_fetch_natpool_name_shared = null
  # fp_cert_fetch_natpool_precedence - (optional) is a type of number
  fp_cert_fetch_natpool_precedence = null
  # handshake_logging_enable - (optional) is a type of number
  handshake_logging_enable = null
  # hsm_type - (optional) is a type of string
  hsm_type = null
  # inspect_certificate_issuer_cl_name - (optional) is a type of string
  inspect_certificate_issuer_cl_name = null
  # inspect_certificate_san_cl_name - (optional) is a type of string
  inspect_certificate_san_cl_name = null
  # inspect_certificate_subject_cl_name - (optional) is a type of string
  inspect_certificate_subject_cl_name = null
  # inspect_list_name - (optional) is a type of string
  inspect_list_name = null
  # key_alt_encrypted - (optional) is a type of string
  key_alt_encrypted = null
  # key_alt_passphrase - (optional) is a type of string
  key_alt_passphrase = null
  # key_alternate - (optional) is a type of string
  key_alternate = null
  # key_encrypted - (optional) is a type of string
  key_encrypted = null
  # key_passphrase - (optional) is a type of string
  key_passphrase = null
  # key_shared_encrypted - (optional) is a type of string
  key_shared_encrypted = null
  # key_shared_passphrase - (optional) is a type of string
  key_shared_passphrase = null
  # key_shared_str - (optional) is a type of string
  key_shared_str = null
  # key_str - (optional) is a type of string
  key_str = null
  # ldap_base_dn_from_cert - (optional) is a type of number
  ldap_base_dn_from_cert = null
  # ldap_search_filter - (optional) is a type of string
  ldap_search_filter = null
  # local_logging - (optional) is a type of number
  local_logging = null
  # name - (optional) is a type of string
  name = null
  # no_shared_cipher_action - (optional) is a type of string
  no_shared_cipher_action = null
  # non_ssl_bypass_l4session - (optional) is a type of number
  non_ssl_bypass_l4session = null
  # non_ssl_bypass_service_group - (optional) is a type of string
  non_ssl_bypass_service_group = null
  # notafter - (optional) is a type of number
  notafter = null
  # notafterday - (optional) is a type of number
  notafterday = null
  # notaftermonth - (optional) is a type of number
  notaftermonth = null
  # notafteryear - (optional) is a type of number
  notafteryear = null
  # notbefore - (optional) is a type of number
  notbefore = null
  # notbeforeday - (optional) is a type of number
  notbeforeday = null
  # notbeforemonth - (optional) is a type of number
  notbeforemonth = null
  # notbeforeyear - (optional) is a type of number
  notbeforeyear = null
  # ocsp_stapling - (optional) is a type of number
  ocsp_stapling = null
  # ocspst_ca_cert - (optional) is a type of string
  ocspst_ca_cert = null
  # ocspst_ocsp - (optional) is a type of number
  ocspst_ocsp = null
  # ocspst_sg - (optional) is a type of string
  ocspst_sg = null
  # ocspst_sg_days - (optional) is a type of number
  ocspst_sg_days = null
  # ocspst_sg_hours - (optional) is a type of number
  ocspst_sg_hours = null
  # ocspst_sg_minutes - (optional) is a type of number
  ocspst_sg_minutes = null
  # ocspst_sg_timeout - (optional) is a type of number
  ocspst_sg_timeout = null
  # ocspst_srvr - (optional) is a type of string
  ocspst_srvr = null
  # ocspst_srvr_days - (optional) is a type of number
  ocspst_srvr_days = null
  # ocspst_srvr_hours - (optional) is a type of number
  ocspst_srvr_hours = null
  # ocspst_srvr_minutes - (optional) is a type of number
  ocspst_srvr_minutes = null
  # ocspst_srvr_timeout - (optional) is a type of number
  ocspst_srvr_timeout = null
  # renegotiation_disable - (optional) is a type of number
  renegotiation_disable = null
  # require_web_category - (optional) is a type of number
  require_web_category = null
  # server_name_auto_map - (optional) is a type of number
  server_name_auto_map = null
  # session_cache_size - (optional) is a type of number
  session_cache_size = null
  # session_cache_timeout - (optional) is a type of number
  session_cache_timeout = null
  # session_ticket_lifetime - (optional) is a type of number
  session_ticket_lifetime = null
  # shared_partition_cipher_template - (optional) is a type of number
  shared_partition_cipher_template = null
  # shared_partition_pool - (optional) is a type of number
  shared_partition_pool = null
  # sni_enable_log - (optional) is a type of number
  sni_enable_log = null
  # ssl_false_start_disable - (optional) is a type of number
  ssl_false_start_disable = null
  # ssli_logging - (optional) is a type of number
  ssli_logging = null
  # sslilogging - (optional) is a type of string
  sslilogging = null
  # sslv2_bypass_service_group - (optional) is a type of string
  sslv2_bypass_service_group = null
  # template_cipher - (optional) is a type of string
  template_cipher = null
  # template_cipher_shared - (optional) is a type of string
  template_cipher_shared = null
  # template_hsm - (optional) is a type of string
  template_hsm = null
  # user_name_list - (optional) is a type of string
  user_name_list = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
  # verify_cert_fail_action - (optional) is a type of string
  verify_cert_fail_action = null
  # version - (optional) is a type of number
  version = null

  bypass_cert_issuer_multi_class_list = [{
    bypass_cert_issuer_multi_class_list_name = null
  }]

  bypass_cert_san_multi_class_list = [{
    bypass_cert_san_multi_class_list_name = null
  }]

  bypass_cert_subject_multi_class_list = [{
    bypass_cert_subject_multi_class_list_name = null
  }]

  ca_certs = [{
    ca_cert          = null
    ca_shared        = null
    client_ocsp      = null
    client_ocsp_sg   = null
    client_ocsp_srvr = null
  }]

  certificate_issuer_contains_list = [{
    certificate_issuer_contains = null
  }]

  certificate_issuer_ends_with_list = [{
    certificate_issuer_ends_with = null
  }]

  certificate_issuer_equals_list = [{
    certificate_issuer_equals = null
  }]

  certificate_issuer_starts_with_list = [{
    certificate_issuer_starts = null
  }]

  certificate_san_contains_list = [{
    certificate_san_contains = null
  }]

  certificate_san_ends_with_list = [{
    certificate_san_ends_with = null
  }]

  certificate_san_equals_list = [{
    certificate_san_equals = null
  }]

  certificate_san_starts_with_list = [{
    certificate_san_starts = null
  }]

  certificate_subject_contains_list = [{
    certificate_subject_contains = null
  }]

  certificate_subject_ends_with_list = [{
    certificate_subject_ends_with = null
  }]

  certificate_subject_equals_list = [{
    certificate_subject_equals = null
  }]

  certificate_subject_starts_with_list = [{
    certificate_subject_starts = null
  }]

  cipher_without_prio_list = [{
    cipher_wo_prio = null
  }]

  client_auth_contains_list = [{
    client_auth_contains = null
  }]

  client_auth_ends_with_list = [{
    client_auth_ends_with = null
  }]

  client_auth_equals_list = [{
    client_auth_equals = null
  }]

  client_auth_starts_with_list = [{
    client_auth_starts_with = null
  }]

  contains_list = [{
    contains = null
  }]

  crl_certs = [{
    crl        = null
    crl_shared = null
  }]

  ec_list = [{
    ec = null
  }]

  ends_with_list = [{
    ends_with = null
  }]

  equals_list = [{
    equals = null
  }]

  forward_proxy_trusted_ca_lists = [{
    forward_proxy_trusted_ca = null
  }]

  multi_class_list = [{
    multi_clist_name = null
  }]

  req_ca_lists = [{
    client_certificate_request_ca = null
  }]

  sampling_enable = [{
    counters1 = null
  }]

  server_name_list = [{
    server_cert                 = null
    server_cert_regex           = null
    server_chain                = null
    server_chain_regex          = null
    server_encrypted            = null
    server_encrypted_regex      = null
    server_key                  = null
    server_key_regex            = null
    server_name                 = null
    server_name_alternate       = null
    server_name_regex           = null
    server_name_regex_alternate = null
    server_passphrase           = null
    server_passphrase_regex     = null
    server_shared               = null
    server_shared_regex         = null
  }]

  starts_with_list = [{
    starts_with = null
  }]

  web_category = [{
    abortion                       = null
    adult_and_pornography          = null
    alcohol_and_tobacco            = null
    auctions                       = null
    bot_nets                       = null
    business_and_economy           = null
    cdns                           = null
    cheating                       = null
    computer_and_internet_info     = null
    computer_and_internet_security = null
    confirmed_spam_sources         = null
    cult_and_occult                = null
    dating                         = null
    dead_sites                     = null
    drugs                          = null
    dynamic_comment                = null
    educational_institutions       = null
    entertainment_and_arts         = null
    fashion_and_beauty             = null
    financial_services             = null
    food_and_dining                = null
    gambling                       = null
    games                          = null
    government                     = null
    gross                          = null
    hacking                        = null
    hate_and_racism                = null
    health_and_medicine            = null
    home_and_garden                = null
    hunting_and_fishing            = null
    illegal                        = null
    image_and_video_search         = null
    internet_communications        = null
    internet_portals               = null
    job_search                     = null
    keyloggers_and_monitoring      = null
    kids                           = null
    legal                          = null
    local_information              = null
    malware_sites                  = null
    marijuana                      = null
    military                       = null
    motor_vehicles                 = null
    music                          = null
    news_and_media                 = null
    nudity                         = null
    online_greeting_cards          = null
    open_http_proxies              = null
    parked_domains                 = null
    pay_to_surf                    = null
    peer_to_peer                   = null
    personal_sites_and_blogs       = null
    personal_storage               = null
    philosophy_and_politics        = null
    phishing_and_other_fraud       = null
    private_ip_addresses           = null
    proxy_avoid_and_anonymizers    = null
    questionable                   = null
    real_estate                    = null
    recreation_and_hobbies         = null
    reference_and_research         = null
    religion                       = null
    search_engines                 = null
    sex_education                  = null
    shareware_and_freeware         = null
    shopping                       = null
    social_network                 = null
    society                        = null
    spam_urls                      = null
    sports                         = null
    spyware_and_adware             = null
    stock_advice_and_tools         = null
    streaming_media                = null
    swimsuits_and_intimate_apparel = null
    training_and_tools             = null
    translation                    = null
    travel                         = null
    uncategorized                  = null
    unconfirmed_spam_sources       = null
    violence                       = null
    weapons                        = null
    web_advertisements             = null
    web_based_email                = null
    web_hosting_sites              = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "ad_group_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alert_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_sg" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_sg_dn" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auth_sg_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_username_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authen_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authorization" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "bypass_cert_issuer_class_list_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bypass_cert_san_class_list_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bypass_cert_subject_class_list_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cache_persistence_list_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "case_insensitive" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cert_alternate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cert_revoke_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cert_shared_str" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cert_str" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cert_unknown_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "chain_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "chain_cert_shared_str" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "class_list_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "client_auth_case_insensitive" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "client_auth_class_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "client_certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "close_notify" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dgversion" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dh_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "direct_client_server_auth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "disable_sslv3" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enable_tls_alert_logging" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "exception_ad_group_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "exception_certificate_issuer_cl_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "exception_certificate_san_cl_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "exception_certificate_subject_cl_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "exception_sni_cl_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "exception_user_name_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expire_hours" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_encrypted" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forward_passphrase" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forward_proxy_alt_sign" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_proxy_block_message" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forward_proxy_ca_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forward_proxy_ca_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forward_proxy_cert_cache_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_proxy_cert_cache_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_proxy_cert_expiry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_proxy_cert_not_ready_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forward_proxy_cert_revoke_action" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_proxy_cert_unknown_action" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_proxy_crl_disable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_proxy_decrypted_dscp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_proxy_decrypted_dscp_bypass" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_proxy_enable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_proxy_failsafe_disable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_proxy_log_disable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_proxy_no_shared_cipher_action" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_proxy_no_sni_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forward_proxy_ocsp_disable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_proxy_selfsign_redir" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_proxy_ssl_version" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_proxy_verify_cert_fail_action" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fp_alt_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fp_alt_encrypted" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fp_alt_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fp_alt_passphrase" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fp_cert_ext_aia_ca_issuers" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fp_cert_ext_aia_ocsp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fp_cert_ext_crldp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fp_cert_fetch_autonat" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fp_cert_fetch_autonat_precedence" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fp_cert_fetch_natpool_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fp_cert_fetch_natpool_name_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fp_cert_fetch_natpool_precedence" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "handshake_logging_enable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hsm_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "inspect_certificate_issuer_cl_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "inspect_certificate_san_cl_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "inspect_certificate_subject_cl_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "inspect_list_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_alt_encrypted" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_alt_passphrase" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_alternate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_encrypted" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_passphrase" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_shared_encrypted" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_shared_passphrase" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_shared_str" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_str" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ldap_base_dn_from_cert" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ldap_search_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_logging" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "no_shared_cipher_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "non_ssl_bypass_l4session" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "non_ssl_bypass_service_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "notafter" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "notafterday" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "notaftermonth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "notafteryear" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "notbefore" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "notbeforeday" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "notbeforemonth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "notbeforeyear" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ocsp_stapling" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ocspst_ca_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ocspst_ocsp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ocspst_sg" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ocspst_sg_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ocspst_sg_hours" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ocspst_sg_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ocspst_sg_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ocspst_srvr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ocspst_srvr_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ocspst_srvr_hours" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ocspst_srvr_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ocspst_srvr_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "renegotiation_disable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "require_web_category" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "server_name_auto_map" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "session_cache_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "session_cache_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "session_ticket_lifetime" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_cipher_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_pool" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sni_enable_log" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssl_false_start_disable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssli_logging" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sslilogging" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sslv2_bypass_service_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_cipher" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_cipher_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_hsm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_name_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "verify_cert_fail_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "bypass_cert_issuer_multi_class_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      bypass_cert_issuer_multi_class_list_name = string
    }
  ))
  default = []
}

variable "bypass_cert_san_multi_class_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      bypass_cert_san_multi_class_list_name = string
    }
  ))
  default = []
}

variable "bypass_cert_subject_multi_class_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      bypass_cert_subject_multi_class_list_name = string
    }
  ))
  default = []
}

variable "ca_certs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ca_cert          = string
      ca_shared        = number
      client_ocsp      = number
      client_ocsp_sg   = string
      client_ocsp_srvr = string
    }
  ))
  default = []
}

variable "certificate_issuer_contains_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate_issuer_contains = string
    }
  ))
  default = []
}

variable "certificate_issuer_ends_with_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate_issuer_ends_with = string
    }
  ))
  default = []
}

variable "certificate_issuer_equals_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate_issuer_equals = string
    }
  ))
  default = []
}

variable "certificate_issuer_starts_with_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate_issuer_starts = string
    }
  ))
  default = []
}

variable "certificate_san_contains_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate_san_contains = string
    }
  ))
  default = []
}

variable "certificate_san_ends_with_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate_san_ends_with = string
    }
  ))
  default = []
}

variable "certificate_san_equals_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate_san_equals = string
    }
  ))
  default = []
}

variable "certificate_san_starts_with_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate_san_starts = string
    }
  ))
  default = []
}

variable "certificate_subject_contains_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate_subject_contains = string
    }
  ))
  default = []
}

variable "certificate_subject_ends_with_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate_subject_ends_with = string
    }
  ))
  default = []
}

variable "certificate_subject_equals_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate_subject_equals = string
    }
  ))
  default = []
}

variable "certificate_subject_starts_with_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate_subject_starts = string
    }
  ))
  default = []
}

variable "cipher_without_prio_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cipher_wo_prio = string
    }
  ))
  default = []
}

variable "client_auth_contains_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      client_auth_contains = string
    }
  ))
  default = []
}

variable "client_auth_ends_with_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      client_auth_ends_with = string
    }
  ))
  default = []
}

variable "client_auth_equals_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      client_auth_equals = string
    }
  ))
  default = []
}

variable "client_auth_starts_with_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      client_auth_starts_with = string
    }
  ))
  default = []
}

variable "contains_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      contains = string
    }
  ))
  default = []
}

variable "crl_certs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      crl        = string
      crl_shared = number
    }
  ))
  default = []
}

variable "ec_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ec = string
    }
  ))
  default = []
}

variable "ends_with_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ends_with = string
    }
  ))
  default = []
}

variable "equals_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      equals = string
    }
  ))
  default = []
}

variable "forward_proxy_trusted_ca_lists" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      forward_proxy_trusted_ca = string
    }
  ))
  default = []
}

variable "multi_class_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      multi_clist_name = string
    }
  ))
  default = []
}

variable "req_ca_lists" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      client_certificate_request_ca = string
    }
  ))
  default = []
}

variable "sampling_enable" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      counters1 = string
    }
  ))
  default = []
}

variable "server_name_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      server_cert                 = string
      server_cert_regex           = string
      server_chain                = string
      server_chain_regex          = string
      server_encrypted            = string
      server_encrypted_regex      = string
      server_key                  = string
      server_key_regex            = string
      server_name                 = string
      server_name_alternate       = number
      server_name_regex           = string
      server_name_regex_alternate = number
      server_passphrase           = string
      server_passphrase_regex     = string
      server_shared               = number
      server_shared_regex         = number
    }
  ))
  default = []
}

variable "starts_with_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      starts_with = string
    }
  ))
  default = []
}

variable "web_category" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      abortion                       = number
      adult_and_pornography          = number
      alcohol_and_tobacco            = number
      auctions                       = number
      bot_nets                       = number
      business_and_economy           = number
      cdns                           = number
      cheating                       = number
      computer_and_internet_info     = number
      computer_and_internet_security = number
      confirmed_spam_sources         = number
      cult_and_occult                = number
      dating                         = number
      dead_sites                     = number
      drugs                          = number
      dynamic_comment                = number
      educational_institutions       = number
      entertainment_and_arts         = number
      fashion_and_beauty             = number
      financial_services             = number
      food_and_dining                = number
      gambling                       = number
      games                          = number
      government                     = number
      gross                          = number
      hacking                        = number
      hate_and_racism                = number
      health_and_medicine            = number
      home_and_garden                = number
      hunting_and_fishing            = number
      illegal                        = number
      image_and_video_search         = number
      internet_communications        = number
      internet_portals               = number
      job_search                     = number
      keyloggers_and_monitoring      = number
      kids                           = number
      legal                          = number
      local_information              = number
      malware_sites                  = number
      marijuana                      = number
      military                       = number
      motor_vehicles                 = number
      music                          = number
      news_and_media                 = number
      nudity                         = number
      online_greeting_cards          = number
      open_http_proxies              = number
      parked_domains                 = number
      pay_to_surf                    = number
      peer_to_peer                   = number
      personal_sites_and_blogs       = number
      personal_storage               = number
      philosophy_and_politics        = number
      phishing_and_other_fraud       = number
      private_ip_addresses           = number
      proxy_avoid_and_anonymizers    = number
      questionable                   = number
      real_estate                    = number
      recreation_and_hobbies         = number
      reference_and_research         = number
      religion                       = number
      search_engines                 = number
      sex_education                  = number
      shareware_and_freeware         = number
      shopping                       = number
      social_network                 = number
      society                        = number
      spam_urls                      = number
      sports                         = number
      spyware_and_adware             = number
      stock_advice_and_tools         = number
      streaming_media                = number
      swimsuits_and_intimate_apparel = number
      training_and_tools             = number
      translation                    = number
      travel                         = number
      uncategorized                  = number
      unconfirmed_spam_sources       = number
      violence                       = number
      weapons                        = number
      web_advertisements             = number
      web_based_email                = number
      web_hosting_sites              = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_client_ssl" "this" {
  ad_group_list                         = var.ad_group_list
  alert_type                            = var.alert_type
  auth_sg                               = var.auth_sg
  auth_sg_dn                            = var.auth_sg_dn
  auth_sg_filter                        = var.auth_sg_filter
  auth_username                         = var.auth_username
  auth_username_attribute               = var.auth_username_attribute
  authen_name                           = var.authen_name
  authorization                         = var.authorization
  bypass_cert_issuer_class_list_name    = var.bypass_cert_issuer_class_list_name
  bypass_cert_san_class_list_name       = var.bypass_cert_san_class_list_name
  bypass_cert_subject_class_list_name   = var.bypass_cert_subject_class_list_name
  cache_persistence_list_name           = var.cache_persistence_list_name
  case_insensitive                      = var.case_insensitive
  cert_alternate                        = var.cert_alternate
  cert_revoke_action                    = var.cert_revoke_action
  cert_shared_str                       = var.cert_shared_str
  cert_str                              = var.cert_str
  cert_unknown_action                   = var.cert_unknown_action
  chain_cert                            = var.chain_cert
  chain_cert_shared_str                 = var.chain_cert_shared_str
  class_list_name                       = var.class_list_name
  client_auth_case_insensitive          = var.client_auth_case_insensitive
  client_auth_class_list                = var.client_auth_class_list
  client_certificate                    = var.client_certificate
  close_notify                          = var.close_notify
  dgversion                             = var.dgversion
  dh_type                               = var.dh_type
  direct_client_server_auth             = var.direct_client_server_auth
  disable_sslv3                         = var.disable_sslv3
  enable_tls_alert_logging              = var.enable_tls_alert_logging
  exception_ad_group_list               = var.exception_ad_group_list
  exception_certificate_issuer_cl_name  = var.exception_certificate_issuer_cl_name
  exception_certificate_san_cl_name     = var.exception_certificate_san_cl_name
  exception_certificate_subject_cl_name = var.exception_certificate_subject_cl_name
  exception_sni_cl_name                 = var.exception_sni_cl_name
  exception_user_name_list              = var.exception_user_name_list
  expire_hours                          = var.expire_hours
  forward_encrypted                     = var.forward_encrypted
  forward_passphrase                    = var.forward_passphrase
  forward_proxy_alt_sign                = var.forward_proxy_alt_sign
  forward_proxy_block_message           = var.forward_proxy_block_message
  forward_proxy_ca_cert                 = var.forward_proxy_ca_cert
  forward_proxy_ca_key                  = var.forward_proxy_ca_key
  forward_proxy_cert_cache_limit        = var.forward_proxy_cert_cache_limit
  forward_proxy_cert_cache_timeout      = var.forward_proxy_cert_cache_timeout
  forward_proxy_cert_expiry             = var.forward_proxy_cert_expiry
  forward_proxy_cert_not_ready_action   = var.forward_proxy_cert_not_ready_action
  forward_proxy_cert_revoke_action      = var.forward_proxy_cert_revoke_action
  forward_proxy_cert_unknown_action     = var.forward_proxy_cert_unknown_action
  forward_proxy_crl_disable             = var.forward_proxy_crl_disable
  forward_proxy_decrypted_dscp          = var.forward_proxy_decrypted_dscp
  forward_proxy_decrypted_dscp_bypass   = var.forward_proxy_decrypted_dscp_bypass
  forward_proxy_enable                  = var.forward_proxy_enable
  forward_proxy_failsafe_disable        = var.forward_proxy_failsafe_disable
  forward_proxy_log_disable             = var.forward_proxy_log_disable
  forward_proxy_no_shared_cipher_action = var.forward_proxy_no_shared_cipher_action
  forward_proxy_no_sni_action           = var.forward_proxy_no_sni_action
  forward_proxy_ocsp_disable            = var.forward_proxy_ocsp_disable
  forward_proxy_selfsign_redir          = var.forward_proxy_selfsign_redir
  forward_proxy_ssl_version             = var.forward_proxy_ssl_version
  forward_proxy_verify_cert_fail_action = var.forward_proxy_verify_cert_fail_action
  fp_alt_cert                           = var.fp_alt_cert
  fp_alt_encrypted                      = var.fp_alt_encrypted
  fp_alt_key                            = var.fp_alt_key
  fp_alt_passphrase                     = var.fp_alt_passphrase
  fp_cert_ext_aia_ca_issuers            = var.fp_cert_ext_aia_ca_issuers
  fp_cert_ext_aia_ocsp                  = var.fp_cert_ext_aia_ocsp
  fp_cert_ext_crldp                     = var.fp_cert_ext_crldp
  fp_cert_fetch_autonat                 = var.fp_cert_fetch_autonat
  fp_cert_fetch_autonat_precedence      = var.fp_cert_fetch_autonat_precedence
  fp_cert_fetch_natpool_name            = var.fp_cert_fetch_natpool_name
  fp_cert_fetch_natpool_name_shared     = var.fp_cert_fetch_natpool_name_shared
  fp_cert_fetch_natpool_precedence      = var.fp_cert_fetch_natpool_precedence
  handshake_logging_enable              = var.handshake_logging_enable
  hsm_type                              = var.hsm_type
  inspect_certificate_issuer_cl_name    = var.inspect_certificate_issuer_cl_name
  inspect_certificate_san_cl_name       = var.inspect_certificate_san_cl_name
  inspect_certificate_subject_cl_name   = var.inspect_certificate_subject_cl_name
  inspect_list_name                     = var.inspect_list_name
  key_alt_encrypted                     = var.key_alt_encrypted
  key_alt_passphrase                    = var.key_alt_passphrase
  key_alternate                         = var.key_alternate
  key_encrypted                         = var.key_encrypted
  key_passphrase                        = var.key_passphrase
  key_shared_encrypted                  = var.key_shared_encrypted
  key_shared_passphrase                 = var.key_shared_passphrase
  key_shared_str                        = var.key_shared_str
  key_str                               = var.key_str
  ldap_base_dn_from_cert                = var.ldap_base_dn_from_cert
  ldap_search_filter                    = var.ldap_search_filter
  local_logging                         = var.local_logging
  name                                  = var.name
  no_shared_cipher_action               = var.no_shared_cipher_action
  non_ssl_bypass_l4session              = var.non_ssl_bypass_l4session
  non_ssl_bypass_service_group          = var.non_ssl_bypass_service_group
  notafter                              = var.notafter
  notafterday                           = var.notafterday
  notaftermonth                         = var.notaftermonth
  notafteryear                          = var.notafteryear
  notbefore                             = var.notbefore
  notbeforeday                          = var.notbeforeday
  notbeforemonth                        = var.notbeforemonth
  notbeforeyear                         = var.notbeforeyear
  ocsp_stapling                         = var.ocsp_stapling
  ocspst_ca_cert                        = var.ocspst_ca_cert
  ocspst_ocsp                           = var.ocspst_ocsp
  ocspst_sg                             = var.ocspst_sg
  ocspst_sg_days                        = var.ocspst_sg_days
  ocspst_sg_hours                       = var.ocspst_sg_hours
  ocspst_sg_minutes                     = var.ocspst_sg_minutes
  ocspst_sg_timeout                     = var.ocspst_sg_timeout
  ocspst_srvr                           = var.ocspst_srvr
  ocspst_srvr_days                      = var.ocspst_srvr_days
  ocspst_srvr_hours                     = var.ocspst_srvr_hours
  ocspst_srvr_minutes                   = var.ocspst_srvr_minutes
  ocspst_srvr_timeout                   = var.ocspst_srvr_timeout
  renegotiation_disable                 = var.renegotiation_disable
  require_web_category                  = var.require_web_category
  server_name_auto_map                  = var.server_name_auto_map
  session_cache_size                    = var.session_cache_size
  session_cache_timeout                 = var.session_cache_timeout
  session_ticket_lifetime               = var.session_ticket_lifetime
  shared_partition_cipher_template      = var.shared_partition_cipher_template
  shared_partition_pool                 = var.shared_partition_pool
  sni_enable_log                        = var.sni_enable_log
  ssl_false_start_disable               = var.ssl_false_start_disable
  ssli_logging                          = var.ssli_logging
  sslilogging                           = var.sslilogging
  sslv2_bypass_service_group            = var.sslv2_bypass_service_group
  template_cipher                       = var.template_cipher
  template_cipher_shared                = var.template_cipher_shared
  template_hsm                          = var.template_hsm
  user_name_list                        = var.user_name_list
  user_tag                              = var.user_tag
  uuid                                  = var.uuid
  verify_cert_fail_action               = var.verify_cert_fail_action
  version                               = var.version

  dynamic "bypass_cert_issuer_multi_class_list" {
    for_each = var.bypass_cert_issuer_multi_class_list
    content {
      bypass_cert_issuer_multi_class_list_name = bypass_cert_issuer_multi_class_list.value["bypass_cert_issuer_multi_class_list_name"]
    }
  }

  dynamic "bypass_cert_san_multi_class_list" {
    for_each = var.bypass_cert_san_multi_class_list
    content {
      bypass_cert_san_multi_class_list_name = bypass_cert_san_multi_class_list.value["bypass_cert_san_multi_class_list_name"]
    }
  }

  dynamic "bypass_cert_subject_multi_class_list" {
    for_each = var.bypass_cert_subject_multi_class_list
    content {
      bypass_cert_subject_multi_class_list_name = bypass_cert_subject_multi_class_list.value["bypass_cert_subject_multi_class_list_name"]
    }
  }

  dynamic "ca_certs" {
    for_each = var.ca_certs
    content {
      ca_cert          = ca_certs.value["ca_cert"]
      ca_shared        = ca_certs.value["ca_shared"]
      client_ocsp      = ca_certs.value["client_ocsp"]
      client_ocsp_sg   = ca_certs.value["client_ocsp_sg"]
      client_ocsp_srvr = ca_certs.value["client_ocsp_srvr"]
    }
  }

  dynamic "certificate_issuer_contains_list" {
    for_each = var.certificate_issuer_contains_list
    content {
      certificate_issuer_contains = certificate_issuer_contains_list.value["certificate_issuer_contains"]
    }
  }

  dynamic "certificate_issuer_ends_with_list" {
    for_each = var.certificate_issuer_ends_with_list
    content {
      certificate_issuer_ends_with = certificate_issuer_ends_with_list.value["certificate_issuer_ends_with"]
    }
  }

  dynamic "certificate_issuer_equals_list" {
    for_each = var.certificate_issuer_equals_list
    content {
      certificate_issuer_equals = certificate_issuer_equals_list.value["certificate_issuer_equals"]
    }
  }

  dynamic "certificate_issuer_starts_with_list" {
    for_each = var.certificate_issuer_starts_with_list
    content {
      certificate_issuer_starts = certificate_issuer_starts_with_list.value["certificate_issuer_starts"]
    }
  }

  dynamic "certificate_san_contains_list" {
    for_each = var.certificate_san_contains_list
    content {
      certificate_san_contains = certificate_san_contains_list.value["certificate_san_contains"]
    }
  }

  dynamic "certificate_san_ends_with_list" {
    for_each = var.certificate_san_ends_with_list
    content {
      certificate_san_ends_with = certificate_san_ends_with_list.value["certificate_san_ends_with"]
    }
  }

  dynamic "certificate_san_equals_list" {
    for_each = var.certificate_san_equals_list
    content {
      certificate_san_equals = certificate_san_equals_list.value["certificate_san_equals"]
    }
  }

  dynamic "certificate_san_starts_with_list" {
    for_each = var.certificate_san_starts_with_list
    content {
      certificate_san_starts = certificate_san_starts_with_list.value["certificate_san_starts"]
    }
  }

  dynamic "certificate_subject_contains_list" {
    for_each = var.certificate_subject_contains_list
    content {
      certificate_subject_contains = certificate_subject_contains_list.value["certificate_subject_contains"]
    }
  }

  dynamic "certificate_subject_ends_with_list" {
    for_each = var.certificate_subject_ends_with_list
    content {
      certificate_subject_ends_with = certificate_subject_ends_with_list.value["certificate_subject_ends_with"]
    }
  }

  dynamic "certificate_subject_equals_list" {
    for_each = var.certificate_subject_equals_list
    content {
      certificate_subject_equals = certificate_subject_equals_list.value["certificate_subject_equals"]
    }
  }

  dynamic "certificate_subject_starts_with_list" {
    for_each = var.certificate_subject_starts_with_list
    content {
      certificate_subject_starts = certificate_subject_starts_with_list.value["certificate_subject_starts"]
    }
  }

  dynamic "cipher_without_prio_list" {
    for_each = var.cipher_without_prio_list
    content {
      cipher_wo_prio = cipher_without_prio_list.value["cipher_wo_prio"]
    }
  }

  dynamic "client_auth_contains_list" {
    for_each = var.client_auth_contains_list
    content {
      client_auth_contains = client_auth_contains_list.value["client_auth_contains"]
    }
  }

  dynamic "client_auth_ends_with_list" {
    for_each = var.client_auth_ends_with_list
    content {
      client_auth_ends_with = client_auth_ends_with_list.value["client_auth_ends_with"]
    }
  }

  dynamic "client_auth_equals_list" {
    for_each = var.client_auth_equals_list
    content {
      client_auth_equals = client_auth_equals_list.value["client_auth_equals"]
    }
  }

  dynamic "client_auth_starts_with_list" {
    for_each = var.client_auth_starts_with_list
    content {
      client_auth_starts_with = client_auth_starts_with_list.value["client_auth_starts_with"]
    }
  }

  dynamic "contains_list" {
    for_each = var.contains_list
    content {
      contains = contains_list.value["contains"]
    }
  }

  dynamic "crl_certs" {
    for_each = var.crl_certs
    content {
      crl        = crl_certs.value["crl"]
      crl_shared = crl_certs.value["crl_shared"]
    }
  }

  dynamic "ec_list" {
    for_each = var.ec_list
    content {
      ec = ec_list.value["ec"]
    }
  }

  dynamic "ends_with_list" {
    for_each = var.ends_with_list
    content {
      ends_with = ends_with_list.value["ends_with"]
    }
  }

  dynamic "equals_list" {
    for_each = var.equals_list
    content {
      equals = equals_list.value["equals"]
    }
  }

  dynamic "forward_proxy_trusted_ca_lists" {
    for_each = var.forward_proxy_trusted_ca_lists
    content {
      forward_proxy_trusted_ca = forward_proxy_trusted_ca_lists.value["forward_proxy_trusted_ca"]
    }
  }

  dynamic "multi_class_list" {
    for_each = var.multi_class_list
    content {
      multi_clist_name = multi_class_list.value["multi_clist_name"]
    }
  }

  dynamic "req_ca_lists" {
    for_each = var.req_ca_lists
    content {
      client_certificate_request_ca = req_ca_lists.value["client_certificate_request_ca"]
    }
  }

  dynamic "sampling_enable" {
    for_each = var.sampling_enable
    content {
      counters1 = sampling_enable.value["counters1"]
    }
  }

  dynamic "server_name_list" {
    for_each = var.server_name_list
    content {
      server_cert                 = server_name_list.value["server_cert"]
      server_cert_regex           = server_name_list.value["server_cert_regex"]
      server_chain                = server_name_list.value["server_chain"]
      server_chain_regex          = server_name_list.value["server_chain_regex"]
      server_encrypted            = server_name_list.value["server_encrypted"]
      server_encrypted_regex      = server_name_list.value["server_encrypted_regex"]
      server_key                  = server_name_list.value["server_key"]
      server_key_regex            = server_name_list.value["server_key_regex"]
      server_name                 = server_name_list.value["server_name"]
      server_name_alternate       = server_name_list.value["server_name_alternate"]
      server_name_regex           = server_name_list.value["server_name_regex"]
      server_name_regex_alternate = server_name_list.value["server_name_regex_alternate"]
      server_passphrase           = server_name_list.value["server_passphrase"]
      server_passphrase_regex     = server_name_list.value["server_passphrase_regex"]
      server_shared               = server_name_list.value["server_shared"]
      server_shared_regex         = server_name_list.value["server_shared_regex"]
    }
  }

  dynamic "starts_with_list" {
    for_each = var.starts_with_list
    content {
      starts_with = starts_with_list.value["starts_with"]
    }
  }

  dynamic "web_category" {
    for_each = var.web_category
    content {
      abortion                       = web_category.value["abortion"]
      adult_and_pornography          = web_category.value["adult_and_pornography"]
      alcohol_and_tobacco            = web_category.value["alcohol_and_tobacco"]
      auctions                       = web_category.value["auctions"]
      bot_nets                       = web_category.value["bot_nets"]
      business_and_economy           = web_category.value["business_and_economy"]
      cdns                           = web_category.value["cdns"]
      cheating                       = web_category.value["cheating"]
      computer_and_internet_info     = web_category.value["computer_and_internet_info"]
      computer_and_internet_security = web_category.value["computer_and_internet_security"]
      confirmed_spam_sources         = web_category.value["confirmed_spam_sources"]
      cult_and_occult                = web_category.value["cult_and_occult"]
      dating                         = web_category.value["dating"]
      dead_sites                     = web_category.value["dead_sites"]
      drugs                          = web_category.value["drugs"]
      dynamic_comment                = web_category.value["dynamic_comment"]
      educational_institutions       = web_category.value["educational_institutions"]
      entertainment_and_arts         = web_category.value["entertainment_and_arts"]
      fashion_and_beauty             = web_category.value["fashion_and_beauty"]
      financial_services             = web_category.value["financial_services"]
      food_and_dining                = web_category.value["food_and_dining"]
      gambling                       = web_category.value["gambling"]
      games                          = web_category.value["games"]
      government                     = web_category.value["government"]
      gross                          = web_category.value["gross"]
      hacking                        = web_category.value["hacking"]
      hate_and_racism                = web_category.value["hate_and_racism"]
      health_and_medicine            = web_category.value["health_and_medicine"]
      home_and_garden                = web_category.value["home_and_garden"]
      hunting_and_fishing            = web_category.value["hunting_and_fishing"]
      illegal                        = web_category.value["illegal"]
      image_and_video_search         = web_category.value["image_and_video_search"]
      internet_communications        = web_category.value["internet_communications"]
      internet_portals               = web_category.value["internet_portals"]
      job_search                     = web_category.value["job_search"]
      keyloggers_and_monitoring      = web_category.value["keyloggers_and_monitoring"]
      kids                           = web_category.value["kids"]
      legal                          = web_category.value["legal"]
      local_information              = web_category.value["local_information"]
      malware_sites                  = web_category.value["malware_sites"]
      marijuana                      = web_category.value["marijuana"]
      military                       = web_category.value["military"]
      motor_vehicles                 = web_category.value["motor_vehicles"]
      music                          = web_category.value["music"]
      news_and_media                 = web_category.value["news_and_media"]
      nudity                         = web_category.value["nudity"]
      online_greeting_cards          = web_category.value["online_greeting_cards"]
      open_http_proxies              = web_category.value["open_http_proxies"]
      parked_domains                 = web_category.value["parked_domains"]
      pay_to_surf                    = web_category.value["pay_to_surf"]
      peer_to_peer                   = web_category.value["peer_to_peer"]
      personal_sites_and_blogs       = web_category.value["personal_sites_and_blogs"]
      personal_storage               = web_category.value["personal_storage"]
      philosophy_and_politics        = web_category.value["philosophy_and_politics"]
      phishing_and_other_fraud       = web_category.value["phishing_and_other_fraud"]
      private_ip_addresses           = web_category.value["private_ip_addresses"]
      proxy_avoid_and_anonymizers    = web_category.value["proxy_avoid_and_anonymizers"]
      questionable                   = web_category.value["questionable"]
      real_estate                    = web_category.value["real_estate"]
      recreation_and_hobbies         = web_category.value["recreation_and_hobbies"]
      reference_and_research         = web_category.value["reference_and_research"]
      religion                       = web_category.value["religion"]
      search_engines                 = web_category.value["search_engines"]
      sex_education                  = web_category.value["sex_education"]
      shareware_and_freeware         = web_category.value["shareware_and_freeware"]
      shopping                       = web_category.value["shopping"]
      social_network                 = web_category.value["social_network"]
      society                        = web_category.value["society"]
      spam_urls                      = web_category.value["spam_urls"]
      sports                         = web_category.value["sports"]
      spyware_and_adware             = web_category.value["spyware_and_adware"]
      stock_advice_and_tools         = web_category.value["stock_advice_and_tools"]
      streaming_media                = web_category.value["streaming_media"]
      swimsuits_and_intimate_apparel = web_category.value["swimsuits_and_intimate_apparel"]
      training_and_tools             = web_category.value["training_and_tools"]
      translation                    = web_category.value["translation"]
      travel                         = web_category.value["travel"]
      uncategorized                  = web_category.value["uncategorized"]
      unconfirmed_spam_sources       = web_category.value["unconfirmed_spam_sources"]
      violence                       = web_category.value["violence"]
      weapons                        = web_category.value["weapons"]
      web_advertisements             = web_category.value["web_advertisements"]
      web_based_email                = web_category.value["web_based_email"]
      web_hosting_sites              = web_category.value["web_hosting_sites"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_client_ssl.this.id
}

output "this" {
  value = thunder_slb_template_client_ssl.this
}
```

[top](#index)