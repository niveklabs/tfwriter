---
layout: resource
title: akamai
type: provider
resource: akamai
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "akamai" {
  version = "1.5.0"

  # appsec_section - (optional) is a type of string
  appsec_section = null
  # cache_enabled - (optional) is a type of bool
  cache_enabled = null
  # config_section - (optional) is a type of string
  config_section = null
  # dns_section - (optional) is a type of string
  dns_section = null
  # edgerc - (optional) is a type of string
  edgerc = null
  # gtm_section - (optional) is a type of string
  gtm_section = null
  # networklist_section - (optional) is a type of string
  networklist_section = null
  # papi_section - (optional) is a type of string
  papi_section = null
  # property_section - (optional) is a type of string
  property_section = null

  # NestingSet
  appsec {
    # access_token - (optional) is a type of string
    access_token = null
    # account_key - (optional) is a type of string
    account_key = null
    # client_secret - (optional) is a type of string
    client_secret = null
    # client_token - (optional) is a type of string
    client_token = null
    # host - (optional) is a type of string
    host = null
    # max_body - (optional) is a type of number
    max_body = null
  }

  # NestingSet
  config {
    # access_token - (optional) is a type of string
    access_token = null
    # account_key - (optional) is a type of string
    account_key = null
    # client_secret - (optional) is a type of string
    client_secret = null
    # client_token - (optional) is a type of string
    client_token = null
    # host - (optional) is a type of string
    host = null
    # max_body - (optional) is a type of number
    max_body = null
  }

  # NestingSet
  dns {
    # access_token - (optional) is a type of string
    access_token = null
    # account_key - (optional) is a type of string
    account_key = null
    # client_secret - (optional) is a type of string
    client_secret = null
    # client_token - (optional) is a type of string
    client_token = null
    # host - (optional) is a type of string
    host = null
    # max_body - (optional) is a type of number
    max_body = null
  }

  # NestingSet
  gtm {
    # access_token - (optional) is a type of string
    access_token = null
    # account_key - (optional) is a type of string
    account_key = null
    # client_secret - (optional) is a type of string
    client_secret = null
    # client_token - (optional) is a type of string
    client_token = null
    # host - (optional) is a type of string
    host = null
    # max_body - (optional) is a type of number
    max_body = null
  }

  # NestingSet
  network {
    # access_token - (optional) is a type of string
    access_token = null
    # account_key - (optional) is a type of string
    account_key = null
    # client_secret - (optional) is a type of string
    client_secret = null
    # client_token - (optional) is a type of string
    client_token = null
    # host - (optional) is a type of string
    host = null
    # max_body - (optional) is a type of number
    max_body = null
  }

  # NestingSet
  property {
    # access_token - (optional) is a type of string
    access_token = null
    # account_key - (optional) is a type of string
    account_key = null
    # client_secret - (optional) is a type of string
    client_secret = null
    # client_token - (optional) is a type of string
    client_token = null
    # host - (optional) is a type of string
    host = null
    # max_body - (optional) is a type of number
    max_body = null
  }
}
```

[top](#index)

### Resources


- [akamai_appsec_activations](./r/akamai_appsec_activations.md)

- [akamai_appsec_advanced_settings_logging](./r/akamai_appsec_advanced_settings_logging.md)

- [akamai_appsec_advanced_settings_prefetch](./r/akamai_appsec_advanced_settings_prefetch.md)

- [akamai_appsec_api_request_constraints](./r/akamai_appsec_api_request_constraints.md)

- [akamai_appsec_attack_group_action](./r/akamai_appsec_attack_group_action.md)

- [akamai_appsec_attack_group_condition_exception](./r/akamai_appsec_attack_group_condition_exception.md)

- [akamai_appsec_bypass_network_lists](./r/akamai_appsec_bypass_network_lists.md)

- [akamai_appsec_configuration](./r/akamai_appsec_configuration.md)

- [akamai_appsec_configuration_clone](./r/akamai_appsec_configuration_clone.md)

- [akamai_appsec_configuration_rename](./r/akamai_appsec_configuration_rename.md)

- [akamai_appsec_configuration_version_clone](./r/akamai_appsec_configuration_version_clone.md)

- [akamai_appsec_custom_deny](./r/akamai_appsec_custom_deny.md)

- [akamai_appsec_custom_rule](./r/akamai_appsec_custom_rule.md)

- [akamai_appsec_custom_rule_action](./r/akamai_appsec_custom_rule_action.md)

- [akamai_appsec_eval](./r/akamai_appsec_eval.md)

- [akamai_appsec_eval_hostnames](./r/akamai_appsec_eval_hostnames.md)

- [akamai_appsec_eval_protect_host](./r/akamai_appsec_eval_protect_host.md)

- [akamai_appsec_eval_rule_action](./r/akamai_appsec_eval_rule_action.md)

- [akamai_appsec_eval_rule_condition_exception](./r/akamai_appsec_eval_rule_condition_exception.md)

- [akamai_appsec_ip_geo](./r/akamai_appsec_ip_geo.md)

- [akamai_appsec_match_target](./r/akamai_appsec_match_target.md)

- [akamai_appsec_match_target_sequence](./r/akamai_appsec_match_target_sequence.md)

- [akamai_appsec_penalty_box](./r/akamai_appsec_penalty_box.md)

- [akamai_appsec_rate_policy](./r/akamai_appsec_rate_policy.md)

- [akamai_appsec_rate_policy_action](./r/akamai_appsec_rate_policy_action.md)

- [akamai_appsec_rate_protection](./r/akamai_appsec_rate_protection.md)

- [akamai_appsec_reputation_profile](./r/akamai_appsec_reputation_profile.md)

- [akamai_appsec_reputation_profile_action](./r/akamai_appsec_reputation_profile_action.md)

- [akamai_appsec_reputation_profile_analysis](./r/akamai_appsec_reputation_profile_analysis.md)

- [akamai_appsec_reputation_protection](./r/akamai_appsec_reputation_protection.md)

- [akamai_appsec_rule_action](./r/akamai_appsec_rule_action.md)

- [akamai_appsec_rule_condition_exception](./r/akamai_appsec_rule_condition_exception.md)

- [akamai_appsec_rule_upgrade](./r/akamai_appsec_rule_upgrade.md)

- [akamai_appsec_security_policy](./r/akamai_appsec_security_policy.md)

- [akamai_appsec_security_policy_clone](./r/akamai_appsec_security_policy_clone.md)

- [akamai_appsec_security_policy_protections](./r/akamai_appsec_security_policy_protections.md)

- [akamai_appsec_security_policy_rename](./r/akamai_appsec_security_policy_rename.md)

- [akamai_appsec_selected_hostnames](./r/akamai_appsec_selected_hostnames.md)

- [akamai_appsec_siem_settings](./r/akamai_appsec_siem_settings.md)

- [akamai_appsec_slow_post](./r/akamai_appsec_slow_post.md)

- [akamai_appsec_slowpost_protection](./r/akamai_appsec_slowpost_protection.md)

- [akamai_appsec_version_notes](./r/akamai_appsec_version_notes.md)

- [akamai_appsec_waf_mode](./r/akamai_appsec_waf_mode.md)

- [akamai_appsec_waf_protection](./r/akamai_appsec_waf_protection.md)

- [akamai_cp_code](./r/akamai_cp_code.md)

- [akamai_dns_record](./r/akamai_dns_record.md)

- [akamai_dns_zone](./r/akamai_dns_zone.md)

- [akamai_edge_hostname](./r/akamai_edge_hostname.md)

- [akamai_gtm_asmap](./r/akamai_gtm_asmap.md)

- [akamai_gtm_cidrmap](./r/akamai_gtm_cidrmap.md)

- [akamai_gtm_datacenter](./r/akamai_gtm_datacenter.md)

- [akamai_gtm_domain](./r/akamai_gtm_domain.md)

- [akamai_gtm_geomap](./r/akamai_gtm_geomap.md)

- [akamai_gtm_property](./r/akamai_gtm_property.md)

- [akamai_gtm_resource](./r/akamai_gtm_resource.md)

- [akamai_iam_user](./r/akamai_iam_user.md)

- [akamai_networklist_activations](./r/akamai_networklist_activations.md)

- [akamai_networklist_description](./r/akamai_networklist_description.md)

- [akamai_networklist_network_list](./r/akamai_networklist_network_list.md)

- [akamai_networklist_subscription](./r/akamai_networklist_subscription.md)

- [akamai_property](./r/akamai_property.md)

- [akamai_property_activation](./r/akamai_property_activation.md)

- [akamai_property_variables](./r/akamai_property_variables.md)


[top](#index)

### Datasources


- [akamai_appsec_advanced_settings_logging](./d/akamai_appsec_advanced_settings_logging.md)

- [akamai_appsec_advanced_settings_prefetch](./d/akamai_appsec_advanced_settings_prefetch.md)

- [akamai_appsec_api_endpoints](./d/akamai_appsec_api_endpoints.md)

- [akamai_appsec_api_request_constraints](./d/akamai_appsec_api_request_constraints.md)

- [akamai_appsec_attack_group_actions](./d/akamai_appsec_attack_group_actions.md)

- [akamai_appsec_attack_group_condition_exception](./d/akamai_appsec_attack_group_condition_exception.md)

- [akamai_appsec_bypass_network_lists](./d/akamai_appsec_bypass_network_lists.md)

- [akamai_appsec_configuration](./d/akamai_appsec_configuration.md)

- [akamai_appsec_configuration_version](./d/akamai_appsec_configuration_version.md)

- [akamai_appsec_contracts_groups](./d/akamai_appsec_contracts_groups.md)

- [akamai_appsec_custom_deny](./d/akamai_appsec_custom_deny.md)

- [akamai_appsec_custom_rule_actions](./d/akamai_appsec_custom_rule_actions.md)

- [akamai_appsec_custom_rules](./d/akamai_appsec_custom_rules.md)

- [akamai_appsec_eval](./d/akamai_appsec_eval.md)

- [akamai_appsec_eval_hostnames](./d/akamai_appsec_eval_hostnames.md)

- [akamai_appsec_eval_rule_actions](./d/akamai_appsec_eval_rule_actions.md)

- [akamai_appsec_eval_rule_condition_exception](./d/akamai_appsec_eval_rule_condition_exception.md)

- [akamai_appsec_export_configuration](./d/akamai_appsec_export_configuration.md)

- [akamai_appsec_failover_hostnames](./d/akamai_appsec_failover_hostnames.md)

- [akamai_appsec_hostname_coverage](./d/akamai_appsec_hostname_coverage.md)

- [akamai_appsec_hostname_coverage_match_targets](./d/akamai_appsec_hostname_coverage_match_targets.md)

- [akamai_appsec_hostname_coverage_overlapping](./d/akamai_appsec_hostname_coverage_overlapping.md)

- [akamai_appsec_ip_geo](./d/akamai_appsec_ip_geo.md)

- [akamai_appsec_match_targets](./d/akamai_appsec_match_targets.md)

- [akamai_appsec_penalty_box](./d/akamai_appsec_penalty_box.md)

- [akamai_appsec_rate_policies](./d/akamai_appsec_rate_policies.md)

- [akamai_appsec_rate_policy_actions](./d/akamai_appsec_rate_policy_actions.md)

- [akamai_appsec_reputation_profile_actions](./d/akamai_appsec_reputation_profile_actions.md)

- [akamai_appsec_reputation_profile_analysis](./d/akamai_appsec_reputation_profile_analysis.md)

- [akamai_appsec_reputation_profiles](./d/akamai_appsec_reputation_profiles.md)

- [akamai_appsec_rule_actions](./d/akamai_appsec_rule_actions.md)

- [akamai_appsec_rule_condition_exception](./d/akamai_appsec_rule_condition_exception.md)

- [akamai_appsec_rule_upgrade_details](./d/akamai_appsec_rule_upgrade_details.md)

- [akamai_appsec_security_policy](./d/akamai_appsec_security_policy.md)

- [akamai_appsec_security_policy_protections](./d/akamai_appsec_security_policy_protections.md)

- [akamai_appsec_selectable_hostnames](./d/akamai_appsec_selectable_hostnames.md)

- [akamai_appsec_selected_hostnames](./d/akamai_appsec_selected_hostnames.md)

- [akamai_appsec_siem_definitions](./d/akamai_appsec_siem_definitions.md)

- [akamai_appsec_siem_settings](./d/akamai_appsec_siem_settings.md)

- [akamai_appsec_slow_post](./d/akamai_appsec_slow_post.md)

- [akamai_appsec_version_notes](./d/akamai_appsec_version_notes.md)

- [akamai_appsec_waf_mode](./d/akamai_appsec_waf_mode.md)

- [akamai_authorities_set](./d/akamai_authorities_set.md)

- [akamai_contract](./d/akamai_contract.md)

- [akamai_contracts](./d/akamai_contracts.md)

- [akamai_cp_code](./d/akamai_cp_code.md)

- [akamai_dns_record_set](./d/akamai_dns_record_set.md)

- [akamai_group](./d/akamai_group.md)

- [akamai_groups](./d/akamai_groups.md)

- [akamai_gtm_default_datacenter](./d/akamai_gtm_default_datacenter.md)

- [akamai_iam_contact_types](./d/akamai_iam_contact_types.md)

- [akamai_iam_countries](./d/akamai_iam_countries.md)

- [akamai_iam_groups](./d/akamai_iam_groups.md)

- [akamai_iam_roles](./d/akamai_iam_roles.md)

- [akamai_iam_states](./d/akamai_iam_states.md)

- [akamai_iam_supported_langs](./d/akamai_iam_supported_langs.md)

- [akamai_iam_timeout_policies](./d/akamai_iam_timeout_policies.md)

- [akamai_networklist_network_lists](./d/akamai_networklist_network_lists.md)

- [akamai_properties](./d/akamai_properties.md)

- [akamai_property](./d/akamai_property.md)

- [akamai_property_hostnames](./d/akamai_property_hostnames.md)

- [akamai_property_products](./d/akamai_property_products.md)

- [akamai_property_rule_formats](./d/akamai_property_rule_formats.md)

- [akamai_property_rules](./d/akamai_property_rules.md)

- [akamai_property_rules_template](./d/akamai_property_rules_template.md)


[top](#index)