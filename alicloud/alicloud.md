---
layout: resource
title: alicloud
type: provider
resource: alicloud
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "alicloud" {
  version = "1.120.0"

  # access_key - (optional) is a type of string
  access_key = null
  # account_id - (optional) is a type of string
  account_id = null
  # configuration_source - (optional) is a type of string
  configuration_source = null
  # ecs_role_name - (optional) is a type of string
  ecs_role_name = null
  # fc - (optional) is a type of string
  fc = null
  # log_endpoint - (optional) is a type of string
  log_endpoint = null
  # mns_endpoint - (optional) is a type of string
  mns_endpoint = null
  # ots_instance_name - (optional) is a type of string
  ots_instance_name = null
  # profile - (optional) is a type of string
  profile = null
  # protocol - (optional) is a type of string
  protocol = null
  # region - (optional) is a type of string
  region = null
  # secret_key - (optional) is a type of string
  secret_key = null
  # security_token - (optional) is a type of string
  security_token = null
  # shared_credentials_file - (optional) is a type of string
  shared_credentials_file = null
  # skip_region_validation - (optional) is a type of bool
  skip_region_validation = null
  # source_ip - (optional) is a type of string
  source_ip = null

  # NestingSet
  assume_role {
    # policy - (optional) is a type of string
    policy = null
    # role_arn - (optional) is a type of string
    role_arn = null
    # session_expiration - (optional) is a type of number
    session_expiration = null
    # session_name - (optional) is a type of string
    session_name = null
  }

  # NestingSet
  endpoints {
    # actiontrail - (optional) is a type of string
    actiontrail = null
    # adb - (optional) is a type of string
    adb = null
    # alidns - (optional) is a type of string
    alidns = null
    # alikafka - (optional) is a type of string
    alikafka = null
    # apigateway - (optional) is a type of string
    apigateway = null
    # brain_industrial - (optional) is a type of string
    brain_industrial = null
    # bssopenapi - (optional) is a type of string
    bssopenapi = null
    # cas - (optional) is a type of string
    cas = null
    # cassandra - (optional) is a type of string
    cassandra = null
    # cbn - (optional) is a type of string
    cbn = null
    # cdn - (optional) is a type of string
    cdn = null
    # cen - (optional) is a type of string
    cen = null
    # cms - (optional) is a type of string
    cms = null
    # config - (optional) is a type of string
    config = null
    # cr - (optional) is a type of string
    cr = null
    # cs - (optional) is a type of string
    cs = null
    # datahub - (optional) is a type of string
    datahub = null
    # dcdn - (optional) is a type of string
    dcdn = null
    # ddosbgp - (optional) is a type of string
    ddosbgp = null
    # ddoscoo - (optional) is a type of string
    ddoscoo = null
    # dds - (optional) is a type of string
    dds = null
    # dms_enterprise - (optional) is a type of string
    dms_enterprise = null
    # dns - (optional) is a type of string
    dns = null
    # drds - (optional) is a type of string
    drds = null
    # eci - (optional) is a type of string
    eci = null
    # ecs - (optional) is a type of string
    ecs = null
    # eipanycast - (optional) is a type of string
    eipanycast = null
    # elasticsearch - (optional) is a type of string
    elasticsearch = null
    # emr - (optional) is a type of string
    emr = null
    # ess - (optional) is a type of string
    ess = null
    # fc - (optional) is a type of string
    fc = null
    # fnf - (optional) is a type of string
    fnf = null
    # ga - (optional) is a type of string
    ga = null
    # gpdb - (optional) is a type of string
    gpdb = null
    # hitsdb - (optional) is a type of string
    hitsdb = null
    # ims - (optional) is a type of string
    ims = null
    # kms - (optional) is a type of string
    kms = null
    # kvstore - (optional) is a type of string
    kvstore = null
    # location - (optional) is a type of string
    location = null
    # log - (optional) is a type of string
    log = null
    # market - (optional) is a type of string
    market = null
    # maxcompute - (optional) is a type of string
    maxcompute = null
    # mns - (optional) is a type of string
    mns = null
    # mse - (optional) is a type of string
    mse = null
    # nas - (optional) is a type of string
    nas = null
    # ons - (optional) is a type of string
    ons = null
    # oos - (optional) is a type of string
    oos = null
    # oss - (optional) is a type of string
    oss = null
    # ots - (optional) is a type of string
    ots = null
    # polardb - (optional) is a type of string
    polardb = null
    # privatelink - (optional) is a type of string
    privatelink = null
    # pvtz - (optional) is a type of string
    pvtz = null
    # quotas - (optional) is a type of string
    quotas = null
    # r_kvstore - (optional) is a type of string
    r_kvstore = null
    # ram - (optional) is a type of string
    ram = null
    # rds - (optional) is a type of string
    rds = null
    # resourcemanager - (optional) is a type of string
    resourcemanager = null
    # resourcesharing - (optional) is a type of string
    resourcesharing = null
    # ros - (optional) is a type of string
    ros = null
    # sgw - (optional) is a type of string
    sgw = null
    # slb - (optional) is a type of string
    slb = null
    # sts - (optional) is a type of string
    sts = null
    # vpc - (optional) is a type of string
    vpc = null
    # waf_openapi - (optional) is a type of string
    waf_openapi = null
  }
}
```

[top](#index)

### Resources


- [alicloud_actiontrail](./r/alicloud_actiontrail.md)

- [alicloud_actiontrail_trail](./r/alicloud_actiontrail_trail.md)

- [alicloud_adb_account](./r/alicloud_adb_account.md)

- [alicloud_adb_backup_policy](./r/alicloud_adb_backup_policy.md)

- [alicloud_adb_cluster](./r/alicloud_adb_cluster.md)

- [alicloud_adb_connection](./r/alicloud_adb_connection.md)

- [alicloud_alidns_domain](./r/alicloud_alidns_domain.md)

- [alicloud_alidns_domain_attachment](./r/alicloud_alidns_domain_attachment.md)

- [alicloud_alidns_domain_group](./r/alicloud_alidns_domain_group.md)

- [alicloud_alidns_instance](./r/alicloud_alidns_instance.md)

- [alicloud_alidns_record](./r/alicloud_alidns_record.md)

- [alicloud_alikafka_consumer_group](./r/alicloud_alikafka_consumer_group.md)

- [alicloud_alikafka_instance](./r/alicloud_alikafka_instance.md)

- [alicloud_alikafka_sasl_acl](./r/alicloud_alikafka_sasl_acl.md)

- [alicloud_alikafka_sasl_user](./r/alicloud_alikafka_sasl_user.md)

- [alicloud_alikafka_topic](./r/alicloud_alikafka_topic.md)

- [alicloud_api_gateway_api](./r/alicloud_api_gateway_api.md)

- [alicloud_api_gateway_app](./r/alicloud_api_gateway_app.md)

- [alicloud_api_gateway_app_attachment](./r/alicloud_api_gateway_app_attachment.md)

- [alicloud_api_gateway_group](./r/alicloud_api_gateway_group.md)

- [alicloud_api_gateway_vpc_access](./r/alicloud_api_gateway_vpc_access.md)

- [alicloud_auto_provisioning_group](./r/alicloud_auto_provisioning_group.md)

- [alicloud_brain_industrial_pid_loop](./r/alicloud_brain_industrial_pid_loop.md)

- [alicloud_brain_industrial_pid_organization](./r/alicloud_brain_industrial_pid_organization.md)

- [alicloud_brain_industrial_pid_project](./r/alicloud_brain_industrial_pid_project.md)

- [alicloud_cas_certificate](./r/alicloud_cas_certificate.md)

- [alicloud_cassandra_cluster](./r/alicloud_cassandra_cluster.md)

- [alicloud_cassandra_data_center](./r/alicloud_cassandra_data_center.md)

- [alicloud_cdn_domain](./r/alicloud_cdn_domain.md)

- [alicloud_cdn_domain_config](./r/alicloud_cdn_domain_config.md)

- [alicloud_cdn_domain_new](./r/alicloud_cdn_domain_new.md)

- [alicloud_cen_bandwidth_limit](./r/alicloud_cen_bandwidth_limit.md)

- [alicloud_cen_bandwidth_package](./r/alicloud_cen_bandwidth_package.md)

- [alicloud_cen_bandwidth_package_attachment](./r/alicloud_cen_bandwidth_package_attachment.md)

- [alicloud_cen_flowlog](./r/alicloud_cen_flowlog.md)

- [alicloud_cen_instance](./r/alicloud_cen_instance.md)

- [alicloud_cen_instance_attachment](./r/alicloud_cen_instance_attachment.md)

- [alicloud_cen_instance_grant](./r/alicloud_cen_instance_grant.md)

- [alicloud_cen_private_zone](./r/alicloud_cen_private_zone.md)

- [alicloud_cen_route_entry](./r/alicloud_cen_route_entry.md)

- [alicloud_cen_route_map](./r/alicloud_cen_route_map.md)

- [alicloud_cen_route_service](./r/alicloud_cen_route_service.md)

- [alicloud_cen_vbr_health_check](./r/alicloud_cen_vbr_health_check.md)

- [alicloud_cloud_connect_network](./r/alicloud_cloud_connect_network.md)

- [alicloud_cloud_connect_network_attachment](./r/alicloud_cloud_connect_network_attachment.md)

- [alicloud_cloud_connect_network_grant](./r/alicloud_cloud_connect_network_grant.md)

- [alicloud_cloud_storage_gateway_storage_bundle](./r/alicloud_cloud_storage_gateway_storage_bundle.md)

- [alicloud_cms_alarm](./r/alicloud_cms_alarm.md)

- [alicloud_cms_alarm_contact](./r/alicloud_cms_alarm_contact.md)

- [alicloud_cms_alarm_contact_group](./r/alicloud_cms_alarm_contact_group.md)

- [alicloud_cms_group_metric_rule](./r/alicloud_cms_group_metric_rule.md)

- [alicloud_cms_monitor_group](./r/alicloud_cms_monitor_group.md)

- [alicloud_cms_monitor_group_instances](./r/alicloud_cms_monitor_group_instances.md)

- [alicloud_cms_site_monitor](./r/alicloud_cms_site_monitor.md)

- [alicloud_common_bandwidth_package](./r/alicloud_common_bandwidth_package.md)

- [alicloud_common_bandwidth_package_attachment](./r/alicloud_common_bandwidth_package_attachment.md)

- [alicloud_config_configuration_recorder](./r/alicloud_config_configuration_recorder.md)

- [alicloud_config_delivery_channel](./r/alicloud_config_delivery_channel.md)

- [alicloud_config_rule](./r/alicloud_config_rule.md)

- [alicloud_container_cluster](./r/alicloud_container_cluster.md)

- [alicloud_copy_image](./r/alicloud_copy_image.md)

- [alicloud_cr_ee_namespace](./r/alicloud_cr_ee_namespace.md)

- [alicloud_cr_ee_repo](./r/alicloud_cr_ee_repo.md)

- [alicloud_cr_ee_sync_rule](./r/alicloud_cr_ee_sync_rule.md)

- [alicloud_cr_namespace](./r/alicloud_cr_namespace.md)

- [alicloud_cr_repo](./r/alicloud_cr_repo.md)

- [alicloud_cs_application](./r/alicloud_cs_application.md)

- [alicloud_cs_edge_kubernetes](./r/alicloud_cs_edge_kubernetes.md)

- [alicloud_cs_kubernetes](./r/alicloud_cs_kubernetes.md)

- [alicloud_cs_kubernetes_autoscaler](./r/alicloud_cs_kubernetes_autoscaler.md)

- [alicloud_cs_kubernetes_node_pool](./r/alicloud_cs_kubernetes_node_pool.md)

- [alicloud_cs_managed_kubernetes](./r/alicloud_cs_managed_kubernetes.md)

- [alicloud_cs_serverless_kubernetes](./r/alicloud_cs_serverless_kubernetes.md)

- [alicloud_cs_swarm](./r/alicloud_cs_swarm.md)

- [alicloud_datahub_project](./r/alicloud_datahub_project.md)

- [alicloud_datahub_subscription](./r/alicloud_datahub_subscription.md)

- [alicloud_datahub_topic](./r/alicloud_datahub_topic.md)

- [alicloud_db_account](./r/alicloud_db_account.md)

- [alicloud_db_account_privilege](./r/alicloud_db_account_privilege.md)

- [alicloud_db_backup_policy](./r/alicloud_db_backup_policy.md)

- [alicloud_db_connection](./r/alicloud_db_connection.md)

- [alicloud_db_database](./r/alicloud_db_database.md)

- [alicloud_db_instance](./r/alicloud_db_instance.md)

- [alicloud_db_read_write_splitting_connection](./r/alicloud_db_read_write_splitting_connection.md)

- [alicloud_db_readonly_instance](./r/alicloud_db_readonly_instance.md)

- [alicloud_dcdn_domain](./r/alicloud_dcdn_domain.md)

- [alicloud_ddosbgp_instance](./r/alicloud_ddosbgp_instance.md)

- [alicloud_ddoscoo_instance](./r/alicloud_ddoscoo_instance.md)

- [alicloud_ddoscoo_scheduler_rule](./r/alicloud_ddoscoo_scheduler_rule.md)

- [alicloud_disk](./r/alicloud_disk.md)

- [alicloud_disk_attachment](./r/alicloud_disk_attachment.md)

- [alicloud_dms_enterprise_instance](./r/alicloud_dms_enterprise_instance.md)

- [alicloud_dms_enterprise_user](./r/alicloud_dms_enterprise_user.md)

- [alicloud_dns](./r/alicloud_dns.md)

- [alicloud_dns_domain](./r/alicloud_dns_domain.md)

- [alicloud_dns_domain_attachment](./r/alicloud_dns_domain_attachment.md)

- [alicloud_dns_group](./r/alicloud_dns_group.md)

- [alicloud_dns_instance](./r/alicloud_dns_instance.md)

- [alicloud_dns_record](./r/alicloud_dns_record.md)

- [alicloud_drds_instance](./r/alicloud_drds_instance.md)

- [alicloud_eci_container_group](./r/alicloud_eci_container_group.md)

- [alicloud_eci_image_cache](./r/alicloud_eci_image_cache.md)

- [alicloud_eci_openapi_image_cache](./r/alicloud_eci_openapi_image_cache.md)

- [alicloud_ecs_auto_snapshot_policy](./r/alicloud_ecs_auto_snapshot_policy.md)

- [alicloud_ecs_command](./r/alicloud_ecs_command.md)

- [alicloud_ecs_dedicated_host](./r/alicloud_ecs_dedicated_host.md)

- [alicloud_ecs_hpc_cluster](./r/alicloud_ecs_hpc_cluster.md)

- [alicloud_ecs_launch_template](./r/alicloud_ecs_launch_template.md)

- [alicloud_ecs_snapshot](./r/alicloud_ecs_snapshot.md)

- [alicloud_edas_application](./r/alicloud_edas_application.md)

- [alicloud_edas_application_deployment](./r/alicloud_edas_application_deployment.md)

- [alicloud_edas_application_scale](./r/alicloud_edas_application_scale.md)

- [alicloud_edas_cluster](./r/alicloud_edas_cluster.md)

- [alicloud_edas_deploy_group](./r/alicloud_edas_deploy_group.md)

- [alicloud_edas_instance_cluster_attachment](./r/alicloud_edas_instance_cluster_attachment.md)

- [alicloud_edas_k8s_application](./r/alicloud_edas_k8s_application.md)

- [alicloud_edas_k8s_cluster](./r/alicloud_edas_k8s_cluster.md)

- [alicloud_edas_slb_attachment](./r/alicloud_edas_slb_attachment.md)

- [alicloud_eip](./r/alicloud_eip.md)

- [alicloud_eip_association](./r/alicloud_eip_association.md)

- [alicloud_eipanycast_anycast_eip_address](./r/alicloud_eipanycast_anycast_eip_address.md)

- [alicloud_eipanycast_anycast_eip_address_attachment](./r/alicloud_eipanycast_anycast_eip_address_attachment.md)

- [alicloud_elasticsearch_instance](./r/alicloud_elasticsearch_instance.md)

- [alicloud_emr_cluster](./r/alicloud_emr_cluster.md)

- [alicloud_ess_alarm](./r/alicloud_ess_alarm.md)

- [alicloud_ess_attachment](./r/alicloud_ess_attachment.md)

- [alicloud_ess_lifecycle_hook](./r/alicloud_ess_lifecycle_hook.md)

- [alicloud_ess_notification](./r/alicloud_ess_notification.md)

- [alicloud_ess_scaling_configuration](./r/alicloud_ess_scaling_configuration.md)

- [alicloud_ess_scaling_group](./r/alicloud_ess_scaling_group.md)

- [alicloud_ess_scaling_rule](./r/alicloud_ess_scaling_rule.md)

- [alicloud_ess_scalinggroup_vserver_groups](./r/alicloud_ess_scalinggroup_vserver_groups.md)

- [alicloud_ess_schedule](./r/alicloud_ess_schedule.md)

- [alicloud_ess_scheduled_task](./r/alicloud_ess_scheduled_task.md)

- [alicloud_fc_alias](./r/alicloud_fc_alias.md)

- [alicloud_fc_custom_domain](./r/alicloud_fc_custom_domain.md)

- [alicloud_fc_function](./r/alicloud_fc_function.md)

- [alicloud_fc_function_async_invoke_config](./r/alicloud_fc_function_async_invoke_config.md)

- [alicloud_fc_service](./r/alicloud_fc_service.md)

- [alicloud_fc_trigger](./r/alicloud_fc_trigger.md)

- [alicloud_fnf_flow](./r/alicloud_fnf_flow.md)

- [alicloud_fnf_schedule](./r/alicloud_fnf_schedule.md)

- [alicloud_forward_entry](./r/alicloud_forward_entry.md)

- [alicloud_ga_accelerator](./r/alicloud_ga_accelerator.md)

- [alicloud_ga_bandwidth_package](./r/alicloud_ga_bandwidth_package.md)

- [alicloud_ga_bandwidth_package_attachment](./r/alicloud_ga_bandwidth_package_attachment.md)

- [alicloud_ga_endpoint_group](./r/alicloud_ga_endpoint_group.md)

- [alicloud_ga_forwarding_rule](./r/alicloud_ga_forwarding_rule.md)

- [alicloud_ga_ip_set](./r/alicloud_ga_ip_set.md)

- [alicloud_ga_listener](./r/alicloud_ga_listener.md)

- [alicloud_gpdb_connection](./r/alicloud_gpdb_connection.md)

- [alicloud_gpdb_instance](./r/alicloud_gpdb_instance.md)

- [alicloud_havip](./r/alicloud_havip.md)

- [alicloud_havip_attachment](./r/alicloud_havip_attachment.md)

- [alicloud_hbase_instance](./r/alicloud_hbase_instance.md)

- [alicloud_image](./r/alicloud_image.md)

- [alicloud_image_copy](./r/alicloud_image_copy.md)

- [alicloud_image_export](./r/alicloud_image_export.md)

- [alicloud_image_import](./r/alicloud_image_import.md)

- [alicloud_image_share_permission](./r/alicloud_image_share_permission.md)

- [alicloud_instance](./r/alicloud_instance.md)

- [alicloud_key_pair](./r/alicloud_key_pair.md)

- [alicloud_key_pair_attachment](./r/alicloud_key_pair_attachment.md)

- [alicloud_kms_alias](./r/alicloud_kms_alias.md)

- [alicloud_kms_ciphertext](./r/alicloud_kms_ciphertext.md)

- [alicloud_kms_key](./r/alicloud_kms_key.md)

- [alicloud_kms_key_version](./r/alicloud_kms_key_version.md)

- [alicloud_kms_secret](./r/alicloud_kms_secret.md)

- [alicloud_kvstore_account](./r/alicloud_kvstore_account.md)

- [alicloud_kvstore_backup_policy](./r/alicloud_kvstore_backup_policy.md)

- [alicloud_kvstore_connection](./r/alicloud_kvstore_connection.md)

- [alicloud_kvstore_instance](./r/alicloud_kvstore_instance.md)

- [alicloud_launch_template](./r/alicloud_launch_template.md)

- [alicloud_log_alert](./r/alicloud_log_alert.md)

- [alicloud_log_audit](./r/alicloud_log_audit.md)

- [alicloud_log_dashboard](./r/alicloud_log_dashboard.md)

- [alicloud_log_etl](./r/alicloud_log_etl.md)

- [alicloud_log_machine_group](./r/alicloud_log_machine_group.md)

- [alicloud_log_project](./r/alicloud_log_project.md)

- [alicloud_log_store](./r/alicloud_log_store.md)

- [alicloud_log_store_index](./r/alicloud_log_store_index.md)

- [alicloud_logtail_attachment](./r/alicloud_logtail_attachment.md)

- [alicloud_logtail_config](./r/alicloud_logtail_config.md)

- [alicloud_market_order](./r/alicloud_market_order.md)

- [alicloud_maxcompute_project](./r/alicloud_maxcompute_project.md)

- [alicloud_mns_queue](./r/alicloud_mns_queue.md)

- [alicloud_mns_topic](./r/alicloud_mns_topic.md)

- [alicloud_mns_topic_subscription](./r/alicloud_mns_topic_subscription.md)

- [alicloud_mongodb_instance](./r/alicloud_mongodb_instance.md)

- [alicloud_mongodb_sharding_instance](./r/alicloud_mongodb_sharding_instance.md)

- [alicloud_mse_cluster](./r/alicloud_mse_cluster.md)

- [alicloud_nas_access_group](./r/alicloud_nas_access_group.md)

- [alicloud_nas_access_rule](./r/alicloud_nas_access_rule.md)

- [alicloud_nas_file_system](./r/alicloud_nas_file_system.md)

- [alicloud_nas_mount_target](./r/alicloud_nas_mount_target.md)

- [alicloud_nat_gateway](./r/alicloud_nat_gateway.md)

- [alicloud_network_acl](./r/alicloud_network_acl.md)

- [alicloud_network_acl_attachment](./r/alicloud_network_acl_attachment.md)

- [alicloud_network_acl_entries](./r/alicloud_network_acl_entries.md)

- [alicloud_network_interface](./r/alicloud_network_interface.md)

- [alicloud_network_interface_attachment](./r/alicloud_network_interface_attachment.md)

- [alicloud_ons_group](./r/alicloud_ons_group.md)

- [alicloud_ons_instance](./r/alicloud_ons_instance.md)

- [alicloud_ons_topic](./r/alicloud_ons_topic.md)

- [alicloud_oos_execution](./r/alicloud_oos_execution.md)

- [alicloud_oos_template](./r/alicloud_oos_template.md)

- [alicloud_oss_bucket](./r/alicloud_oss_bucket.md)

- [alicloud_oss_bucket_object](./r/alicloud_oss_bucket_object.md)

- [alicloud_ots_instance](./r/alicloud_ots_instance.md)

- [alicloud_ots_instance_attachment](./r/alicloud_ots_instance_attachment.md)

- [alicloud_ots_table](./r/alicloud_ots_table.md)

- [alicloud_polardb_account](./r/alicloud_polardb_account.md)

- [alicloud_polardb_account_privilege](./r/alicloud_polardb_account_privilege.md)

- [alicloud_polardb_backup_policy](./r/alicloud_polardb_backup_policy.md)

- [alicloud_polardb_cluster](./r/alicloud_polardb_cluster.md)

- [alicloud_polardb_database](./r/alicloud_polardb_database.md)

- [alicloud_polardb_endpoint](./r/alicloud_polardb_endpoint.md)

- [alicloud_polardb_endpoint_address](./r/alicloud_polardb_endpoint_address.md)

- [alicloud_privatelink_vpc_endpoint](./r/alicloud_privatelink_vpc_endpoint.md)

- [alicloud_privatelink_vpc_endpoint_connection](./r/alicloud_privatelink_vpc_endpoint_connection.md)

- [alicloud_privatelink_vpc_endpoint_service](./r/alicloud_privatelink_vpc_endpoint_service.md)

- [alicloud_privatelink_vpc_endpoint_service_resource](./r/alicloud_privatelink_vpc_endpoint_service_resource.md)

- [alicloud_privatelink_vpc_endpoint_service_user](./r/alicloud_privatelink_vpc_endpoint_service_user.md)

- [alicloud_privatelink_vpc_endpoint_zone](./r/alicloud_privatelink_vpc_endpoint_zone.md)

- [alicloud_pvtz_zone](./r/alicloud_pvtz_zone.md)

- [alicloud_pvtz_zone_attachment](./r/alicloud_pvtz_zone_attachment.md)

- [alicloud_pvtz_zone_record](./r/alicloud_pvtz_zone_record.md)

- [alicloud_quotas_application_info](./r/alicloud_quotas_application_info.md)

- [alicloud_quotas_quota_alarm](./r/alicloud_quotas_quota_alarm.md)

- [alicloud_quotas_quota_application](./r/alicloud_quotas_quota_application.md)

- [alicloud_ram_access_key](./r/alicloud_ram_access_key.md)

- [alicloud_ram_account_alias](./r/alicloud_ram_account_alias.md)

- [alicloud_ram_account_password_policy](./r/alicloud_ram_account_password_policy.md)

- [alicloud_ram_alias](./r/alicloud_ram_alias.md)

- [alicloud_ram_group](./r/alicloud_ram_group.md)

- [alicloud_ram_group_membership](./r/alicloud_ram_group_membership.md)

- [alicloud_ram_group_policy_attachment](./r/alicloud_ram_group_policy_attachment.md)

- [alicloud_ram_login_profile](./r/alicloud_ram_login_profile.md)

- [alicloud_ram_policy](./r/alicloud_ram_policy.md)

- [alicloud_ram_role](./r/alicloud_ram_role.md)

- [alicloud_ram_role_attachment](./r/alicloud_ram_role_attachment.md)

- [alicloud_ram_role_policy_attachment](./r/alicloud_ram_role_policy_attachment.md)

- [alicloud_ram_saml_provider](./r/alicloud_ram_saml_provider.md)

- [alicloud_ram_user](./r/alicloud_ram_user.md)

- [alicloud_ram_user_policy_attachment](./r/alicloud_ram_user_policy_attachment.md)

- [alicloud_rds_account](./r/alicloud_rds_account.md)

- [alicloud_rds_parameter_group](./r/alicloud_rds_parameter_group.md)

- [alicloud_reserved_instance](./r/alicloud_reserved_instance.md)

- [alicloud_resource_manager_account](./r/alicloud_resource_manager_account.md)

- [alicloud_resource_manager_control_policy](./r/alicloud_resource_manager_control_policy.md)

- [alicloud_resource_manager_control_policy_attachment](./r/alicloud_resource_manager_control_policy_attachment.md)

- [alicloud_resource_manager_folder](./r/alicloud_resource_manager_folder.md)

- [alicloud_resource_manager_handshake](./r/alicloud_resource_manager_handshake.md)

- [alicloud_resource_manager_policy](./r/alicloud_resource_manager_policy.md)

- [alicloud_resource_manager_policy_attachment](./r/alicloud_resource_manager_policy_attachment.md)

- [alicloud_resource_manager_policy_version](./r/alicloud_resource_manager_policy_version.md)

- [alicloud_resource_manager_resource_directory](./r/alicloud_resource_manager_resource_directory.md)

- [alicloud_resource_manager_resource_group](./r/alicloud_resource_manager_resource_group.md)

- [alicloud_resource_manager_resource_share](./r/alicloud_resource_manager_resource_share.md)

- [alicloud_resource_manager_role](./r/alicloud_resource_manager_role.md)

- [alicloud_resource_manager_shared_resource](./r/alicloud_resource_manager_shared_resource.md)

- [alicloud_resource_manager_shared_target](./r/alicloud_resource_manager_shared_target.md)

- [alicloud_ros_change_set](./r/alicloud_ros_change_set.md)

- [alicloud_ros_stack](./r/alicloud_ros_stack.md)

- [alicloud_ros_stack_group](./r/alicloud_ros_stack_group.md)

- [alicloud_ros_template](./r/alicloud_ros_template.md)

- [alicloud_route_entry](./r/alicloud_route_entry.md)

- [alicloud_route_table](./r/alicloud_route_table.md)

- [alicloud_route_table_attachment](./r/alicloud_route_table_attachment.md)

- [alicloud_router_interface](./r/alicloud_router_interface.md)

- [alicloud_router_interface_connection](./r/alicloud_router_interface_connection.md)

- [alicloud_sag_acl](./r/alicloud_sag_acl.md)

- [alicloud_sag_acl_rule](./r/alicloud_sag_acl_rule.md)

- [alicloud_sag_client_user](./r/alicloud_sag_client_user.md)

- [alicloud_sag_dnat_entry](./r/alicloud_sag_dnat_entry.md)

- [alicloud_sag_qos](./r/alicloud_sag_qos.md)

- [alicloud_sag_qos_car](./r/alicloud_sag_qos_car.md)

- [alicloud_sag_qos_policy](./r/alicloud_sag_qos_policy.md)

- [alicloud_sag_snat_entry](./r/alicloud_sag_snat_entry.md)

- [alicloud_security_group](./r/alicloud_security_group.md)

- [alicloud_security_group_rule](./r/alicloud_security_group_rule.md)

- [alicloud_slb](./r/alicloud_slb.md)

- [alicloud_slb_acl](./r/alicloud_slb_acl.md)

- [alicloud_slb_attachment](./r/alicloud_slb_attachment.md)

- [alicloud_slb_backend_server](./r/alicloud_slb_backend_server.md)

- [alicloud_slb_ca_certificate](./r/alicloud_slb_ca_certificate.md)

- [alicloud_slb_domain_extension](./r/alicloud_slb_domain_extension.md)

- [alicloud_slb_listener](./r/alicloud_slb_listener.md)

- [alicloud_slb_master_slave_server_group](./r/alicloud_slb_master_slave_server_group.md)

- [alicloud_slb_rule](./r/alicloud_slb_rule.md)

- [alicloud_slb_server_certificate](./r/alicloud_slb_server_certificate.md)

- [alicloud_slb_server_group](./r/alicloud_slb_server_group.md)

- [alicloud_snapshot](./r/alicloud_snapshot.md)

- [alicloud_snapshot_policy](./r/alicloud_snapshot_policy.md)

- [alicloud_snat_entry](./r/alicloud_snat_entry.md)

- [alicloud_ssl_vpn_client_cert](./r/alicloud_ssl_vpn_client_cert.md)

- [alicloud_ssl_vpn_server](./r/alicloud_ssl_vpn_server.md)

- [alicloud_subnet](./r/alicloud_subnet.md)

- [alicloud_tsdb_instance](./r/alicloud_tsdb_instance.md)

- [alicloud_vpc](./r/alicloud_vpc.md)

- [alicloud_vpc_flow_log](./r/alicloud_vpc_flow_log.md)

- [alicloud_vpn_connection](./r/alicloud_vpn_connection.md)

- [alicloud_vpn_customer_gateway](./r/alicloud_vpn_customer_gateway.md)

- [alicloud_vpn_gateway](./r/alicloud_vpn_gateway.md)

- [alicloud_vpn_route_entry](./r/alicloud_vpn_route_entry.md)

- [alicloud_vswitch](./r/alicloud_vswitch.md)

- [alicloud_waf_domain](./r/alicloud_waf_domain.md)

- [alicloud_waf_instance](./r/alicloud_waf_instance.md)

- [alicloud_yundun_bastionhost_instance](./r/alicloud_yundun_bastionhost_instance.md)

- [alicloud_yundun_dbaudit_instance](./r/alicloud_yundun_dbaudit_instance.md)


[top](#index)

### Datasources


- [alicloud_account](./d/alicloud_account.md)

- [alicloud_ack_service](./d/alicloud_ack_service.md)

- [alicloud_actiontrail_trails](./d/alicloud_actiontrail_trails.md)

- [alicloud_actiontrails](./d/alicloud_actiontrails.md)

- [alicloud_adb_clusters](./d/alicloud_adb_clusters.md)

- [alicloud_adb_zones](./d/alicloud_adb_zones.md)

- [alicloud_alidns_domain_groups](./d/alicloud_alidns_domain_groups.md)

- [alicloud_alidns_domains](./d/alicloud_alidns_domains.md)

- [alicloud_alidns_instances](./d/alicloud_alidns_instances.md)

- [alicloud_alidns_records](./d/alicloud_alidns_records.md)

- [alicloud_alikafka_consumer_groups](./d/alicloud_alikafka_consumer_groups.md)

- [alicloud_alikafka_instances](./d/alicloud_alikafka_instances.md)

- [alicloud_alikafka_sasl_acls](./d/alicloud_alikafka_sasl_acls.md)

- [alicloud_alikafka_sasl_users](./d/alicloud_alikafka_sasl_users.md)

- [alicloud_alikafka_topics](./d/alicloud_alikafka_topics.md)

- [alicloud_api_gateway_apis](./d/alicloud_api_gateway_apis.md)

- [alicloud_api_gateway_apps](./d/alicloud_api_gateway_apps.md)

- [alicloud_api_gateway_groups](./d/alicloud_api_gateway_groups.md)

- [alicloud_api_gateway_service](./d/alicloud_api_gateway_service.md)

- [alicloud_brain_industrial_pid_loops](./d/alicloud_brain_industrial_pid_loops.md)

- [alicloud_brain_industrial_pid_organizations](./d/alicloud_brain_industrial_pid_organizations.md)

- [alicloud_brain_industrial_pid_projects](./d/alicloud_brain_industrial_pid_projects.md)

- [alicloud_brain_industrial_service](./d/alicloud_brain_industrial_service.md)

- [alicloud_caller_identity](./d/alicloud_caller_identity.md)

- [alicloud_cas_certificates](./d/alicloud_cas_certificates.md)

- [alicloud_cassandra_clusters](./d/alicloud_cassandra_clusters.md)

- [alicloud_cassandra_data_centers](./d/alicloud_cassandra_data_centers.md)

- [alicloud_cassandra_zones](./d/alicloud_cassandra_zones.md)

- [alicloud_cdn_service](./d/alicloud_cdn_service.md)

- [alicloud_cen_bandwidth_limits](./d/alicloud_cen_bandwidth_limits.md)

- [alicloud_cen_bandwidth_packages](./d/alicloud_cen_bandwidth_packages.md)

- [alicloud_cen_flowlogs](./d/alicloud_cen_flowlogs.md)

- [alicloud_cen_instance_attachments](./d/alicloud_cen_instance_attachments.md)

- [alicloud_cen_instances](./d/alicloud_cen_instances.md)

- [alicloud_cen_private_zones](./d/alicloud_cen_private_zones.md)

- [alicloud_cen_region_route_entries](./d/alicloud_cen_region_route_entries.md)

- [alicloud_cen_route_entries](./d/alicloud_cen_route_entries.md)

- [alicloud_cen_route_maps](./d/alicloud_cen_route_maps.md)

- [alicloud_cen_route_services](./d/alicloud_cen_route_services.md)

- [alicloud_cen_vbr_health_checks](./d/alicloud_cen_vbr_health_checks.md)

- [alicloud_cloud_connect_networks](./d/alicloud_cloud_connect_networks.md)

- [alicloud_cloud_storage_gateway_service](./d/alicloud_cloud_storage_gateway_service.md)

- [alicloud_cloud_storage_gateway_storage_bundles](./d/alicloud_cloud_storage_gateway_storage_bundles.md)

- [alicloud_cms_alarm_contact_groups](./d/alicloud_cms_alarm_contact_groups.md)

- [alicloud_cms_alarm_contacts](./d/alicloud_cms_alarm_contacts.md)

- [alicloud_cms_group_metric_rules](./d/alicloud_cms_group_metric_rules.md)

- [alicloud_cms_monitor_group_instances](./d/alicloud_cms_monitor_group_instances.md)

- [alicloud_cms_monitor_group_instanceses](./d/alicloud_cms_monitor_group_instanceses.md)

- [alicloud_cms_monitor_groups](./d/alicloud_cms_monitor_groups.md)

- [alicloud_cms_service](./d/alicloud_cms_service.md)

- [alicloud_common_bandwidth_packages](./d/alicloud_common_bandwidth_packages.md)

- [alicloud_config_configuration_recorders](./d/alicloud_config_configuration_recorders.md)

- [alicloud_config_delivery_channels](./d/alicloud_config_delivery_channels.md)

- [alicloud_config_rules](./d/alicloud_config_rules.md)

- [alicloud_cr_ee_instances](./d/alicloud_cr_ee_instances.md)

- [alicloud_cr_ee_namespaces](./d/alicloud_cr_ee_namespaces.md)

- [alicloud_cr_ee_repos](./d/alicloud_cr_ee_repos.md)

- [alicloud_cr_ee_sync_rules](./d/alicloud_cr_ee_sync_rules.md)

- [alicloud_cr_namespaces](./d/alicloud_cr_namespaces.md)

- [alicloud_cr_repos](./d/alicloud_cr_repos.md)

- [alicloud_cr_service](./d/alicloud_cr_service.md)

- [alicloud_cs_edge_kubernetes_clusters](./d/alicloud_cs_edge_kubernetes_clusters.md)

- [alicloud_cs_kubernetes_clusters](./d/alicloud_cs_kubernetes_clusters.md)

- [alicloud_cs_managed_kubernetes_clusters](./d/alicloud_cs_managed_kubernetes_clusters.md)

- [alicloud_cs_serverless_kubernetes_clusters](./d/alicloud_cs_serverless_kubernetes_clusters.md)

- [alicloud_datahub_service](./d/alicloud_datahub_service.md)

- [alicloud_dataworks_service](./d/alicloud_dataworks_service.md)

- [alicloud_db_instance_classes](./d/alicloud_db_instance_classes.md)

- [alicloud_db_instance_engines](./d/alicloud_db_instance_engines.md)

- [alicloud_db_instances](./d/alicloud_db_instances.md)

- [alicloud_db_zones](./d/alicloud_db_zones.md)

- [alicloud_dcdn_domains](./d/alicloud_dcdn_domains.md)

- [alicloud_dcdn_service](./d/alicloud_dcdn_service.md)

- [alicloud_ddosbgp_instances](./d/alicloud_ddosbgp_instances.md)

- [alicloud_ddoscoo_instances](./d/alicloud_ddoscoo_instances.md)

- [alicloud_disks](./d/alicloud_disks.md)

- [alicloud_dms_enterprise_instances](./d/alicloud_dms_enterprise_instances.md)

- [alicloud_dms_enterprise_users](./d/alicloud_dms_enterprise_users.md)

- [alicloud_dns_domain_groups](./d/alicloud_dns_domain_groups.md)

- [alicloud_dns_domain_records](./d/alicloud_dns_domain_records.md)

- [alicloud_dns_domain_txt_guid](./d/alicloud_dns_domain_txt_guid.md)

- [alicloud_dns_domains](./d/alicloud_dns_domains.md)

- [alicloud_dns_groups](./d/alicloud_dns_groups.md)

- [alicloud_dns_instances](./d/alicloud_dns_instances.md)

- [alicloud_dns_records](./d/alicloud_dns_records.md)

- [alicloud_dns_resolution_lines](./d/alicloud_dns_resolution_lines.md)

- [alicloud_drds_instances](./d/alicloud_drds_instances.md)

- [alicloud_eci_container_groups](./d/alicloud_eci_container_groups.md)

- [alicloud_eci_image_caches](./d/alicloud_eci_image_caches.md)

- [alicloud_ecs_auto_snapshot_policies](./d/alicloud_ecs_auto_snapshot_policies.md)

- [alicloud_ecs_commands](./d/alicloud_ecs_commands.md)

- [alicloud_ecs_dedicated_hosts](./d/alicloud_ecs_dedicated_hosts.md)

- [alicloud_ecs_hpc_clusters](./d/alicloud_ecs_hpc_clusters.md)

- [alicloud_ecs_launch_templates](./d/alicloud_ecs_launch_templates.md)

- [alicloud_ecs_snapshots](./d/alicloud_ecs_snapshots.md)

- [alicloud_edas_applications](./d/alicloud_edas_applications.md)

- [alicloud_edas_clusters](./d/alicloud_edas_clusters.md)

- [alicloud_edas_deploy_groups](./d/alicloud_edas_deploy_groups.md)

- [alicloud_edas_service](./d/alicloud_edas_service.md)

- [alicloud_eipanycast_anycast_eip_addresses](./d/alicloud_eipanycast_anycast_eip_addresses.md)

- [alicloud_eips](./d/alicloud_eips.md)

- [alicloud_elasticsearch_instances](./d/alicloud_elasticsearch_instances.md)

- [alicloud_elasticsearch_zones](./d/alicloud_elasticsearch_zones.md)

- [alicloud_emr_disk_types](./d/alicloud_emr_disk_types.md)

- [alicloud_emr_instance_types](./d/alicloud_emr_instance_types.md)

- [alicloud_emr_main_versions](./d/alicloud_emr_main_versions.md)

- [alicloud_enhanced_nat_available_zones](./d/alicloud_enhanced_nat_available_zones.md)

- [alicloud_ess_alarms](./d/alicloud_ess_alarms.md)

- [alicloud_ess_lifecycle_hooks](./d/alicloud_ess_lifecycle_hooks.md)

- [alicloud_ess_notifications](./d/alicloud_ess_notifications.md)

- [alicloud_ess_scaling_configurations](./d/alicloud_ess_scaling_configurations.md)

- [alicloud_ess_scaling_groups](./d/alicloud_ess_scaling_groups.md)

- [alicloud_ess_scaling_rules](./d/alicloud_ess_scaling_rules.md)

- [alicloud_ess_scheduled_tasks](./d/alicloud_ess_scheduled_tasks.md)

- [alicloud_fc_custom_domains](./d/alicloud_fc_custom_domains.md)

- [alicloud_fc_functions](./d/alicloud_fc_functions.md)

- [alicloud_fc_service](./d/alicloud_fc_service.md)

- [alicloud_fc_services](./d/alicloud_fc_services.md)

- [alicloud_fc_triggers](./d/alicloud_fc_triggers.md)

- [alicloud_fc_zones](./d/alicloud_fc_zones.md)

- [alicloud_file_crc64_checksum](./d/alicloud_file_crc64_checksum.md)

- [alicloud_fnf_flows](./d/alicloud_fnf_flows.md)

- [alicloud_fnf_schedules](./d/alicloud_fnf_schedules.md)

- [alicloud_fnf_service](./d/alicloud_fnf_service.md)

- [alicloud_forward_entries](./d/alicloud_forward_entries.md)

- [alicloud_ga_accelerators](./d/alicloud_ga_accelerators.md)

- [alicloud_ga_bandwidth_packages](./d/alicloud_ga_bandwidth_packages.md)

- [alicloud_ga_endpoint_groups](./d/alicloud_ga_endpoint_groups.md)

- [alicloud_ga_forwarding_rules](./d/alicloud_ga_forwarding_rules.md)

- [alicloud_ga_ip_sets](./d/alicloud_ga_ip_sets.md)

- [alicloud_ga_listeners](./d/alicloud_ga_listeners.md)

- [alicloud_gpdb_instances](./d/alicloud_gpdb_instances.md)

- [alicloud_gpdb_zones](./d/alicloud_gpdb_zones.md)

- [alicloud_havips](./d/alicloud_havips.md)

- [alicloud_hbase_instance_types](./d/alicloud_hbase_instance_types.md)

- [alicloud_hbase_instances](./d/alicloud_hbase_instances.md)

- [alicloud_hbase_zones](./d/alicloud_hbase_zones.md)

- [alicloud_images](./d/alicloud_images.md)

- [alicloud_instance_type_families](./d/alicloud_instance_type_families.md)

- [alicloud_instance_types](./d/alicloud_instance_types.md)

- [alicloud_instances](./d/alicloud_instances.md)

- [alicloud_iot_service](./d/alicloud_iot_service.md)

- [alicloud_key_pairs](./d/alicloud_key_pairs.md)

- [alicloud_kms_aliases](./d/alicloud_kms_aliases.md)

- [alicloud_kms_ciphertext](./d/alicloud_kms_ciphertext.md)

- [alicloud_kms_key_versions](./d/alicloud_kms_key_versions.md)

- [alicloud_kms_keys](./d/alicloud_kms_keys.md)

- [alicloud_kms_plaintext](./d/alicloud_kms_plaintext.md)

- [alicloud_kms_secret_versions](./d/alicloud_kms_secret_versions.md)

- [alicloud_kms_secrets](./d/alicloud_kms_secrets.md)

- [alicloud_kms_service](./d/alicloud_kms_service.md)

- [alicloud_kvstore_accounts](./d/alicloud_kvstore_accounts.md)

- [alicloud_kvstore_connections](./d/alicloud_kvstore_connections.md)

- [alicloud_kvstore_instance_classes](./d/alicloud_kvstore_instance_classes.md)

- [alicloud_kvstore_instance_engines](./d/alicloud_kvstore_instance_engines.md)

- [alicloud_kvstore_instances](./d/alicloud_kvstore_instances.md)

- [alicloud_kvstore_zones](./d/alicloud_kvstore_zones.md)

- [alicloud_log_service](./d/alicloud_log_service.md)

- [alicloud_market_product](./d/alicloud_market_product.md)

- [alicloud_market_products](./d/alicloud_market_products.md)

- [alicloud_maxcompute_service](./d/alicloud_maxcompute_service.md)

- [alicloud_mns_queues](./d/alicloud_mns_queues.md)

- [alicloud_mns_service](./d/alicloud_mns_service.md)

- [alicloud_mns_topic_subscriptions](./d/alicloud_mns_topic_subscriptions.md)

- [alicloud_mns_topics](./d/alicloud_mns_topics.md)

- [alicloud_mongo_instances](./d/alicloud_mongo_instances.md)

- [alicloud_mongodb_instances](./d/alicloud_mongodb_instances.md)

- [alicloud_mongodb_zones](./d/alicloud_mongodb_zones.md)

- [alicloud_mse_clusters](./d/alicloud_mse_clusters.md)

- [alicloud_nas_access_groups](./d/alicloud_nas_access_groups.md)

- [alicloud_nas_access_rules](./d/alicloud_nas_access_rules.md)

- [alicloud_nas_file_systems](./d/alicloud_nas_file_systems.md)

- [alicloud_nas_mount_targets](./d/alicloud_nas_mount_targets.md)

- [alicloud_nas_protocols](./d/alicloud_nas_protocols.md)

- [alicloud_nas_service](./d/alicloud_nas_service.md)

- [alicloud_nat_gateways](./d/alicloud_nat_gateways.md)

- [alicloud_network_interfaces](./d/alicloud_network_interfaces.md)

- [alicloud_ons_groups](./d/alicloud_ons_groups.md)

- [alicloud_ons_instances](./d/alicloud_ons_instances.md)

- [alicloud_ons_service](./d/alicloud_ons_service.md)

- [alicloud_ons_topics](./d/alicloud_ons_topics.md)

- [alicloud_oos_executions](./d/alicloud_oos_executions.md)

- [alicloud_oos_templates](./d/alicloud_oos_templates.md)

- [alicloud_oss_bucket_objects](./d/alicloud_oss_bucket_objects.md)

- [alicloud_oss_buckets](./d/alicloud_oss_buckets.md)

- [alicloud_oss_service](./d/alicloud_oss_service.md)

- [alicloud_ots_instance_attachments](./d/alicloud_ots_instance_attachments.md)

- [alicloud_ots_instances](./d/alicloud_ots_instances.md)

- [alicloud_ots_service](./d/alicloud_ots_service.md)

- [alicloud_ots_tables](./d/alicloud_ots_tables.md)

- [alicloud_polardb_accounts](./d/alicloud_polardb_accounts.md)

- [alicloud_polardb_clusters](./d/alicloud_polardb_clusters.md)

- [alicloud_polardb_databases](./d/alicloud_polardb_databases.md)

- [alicloud_polardb_endpoints](./d/alicloud_polardb_endpoints.md)

- [alicloud_polardb_node_classes](./d/alicloud_polardb_node_classes.md)

- [alicloud_polardb_zones](./d/alicloud_polardb_zones.md)

- [alicloud_privatelink_service](./d/alicloud_privatelink_service.md)

- [alicloud_privatelink_vpc_endpoint_connections](./d/alicloud_privatelink_vpc_endpoint_connections.md)

- [alicloud_privatelink_vpc_endpoint_service_resources](./d/alicloud_privatelink_vpc_endpoint_service_resources.md)

- [alicloud_privatelink_vpc_endpoint_service_users](./d/alicloud_privatelink_vpc_endpoint_service_users.md)

- [alicloud_privatelink_vpc_endpoint_services](./d/alicloud_privatelink_vpc_endpoint_services.md)

- [alicloud_privatelink_vpc_endpoint_zones](./d/alicloud_privatelink_vpc_endpoint_zones.md)

- [alicloud_privatelink_vpc_endpoints](./d/alicloud_privatelink_vpc_endpoints.md)

- [alicloud_pvtz_service](./d/alicloud_pvtz_service.md)

- [alicloud_pvtz_zone_records](./d/alicloud_pvtz_zone_records.md)

- [alicloud_pvtz_zones](./d/alicloud_pvtz_zones.md)

- [alicloud_quotas_application_infos](./d/alicloud_quotas_application_infos.md)

- [alicloud_quotas_quota_alarms](./d/alicloud_quotas_quota_alarms.md)

- [alicloud_quotas_quota_applications](./d/alicloud_quotas_quota_applications.md)

- [alicloud_quotas_quotas](./d/alicloud_quotas_quotas.md)

- [alicloud_ram_account_alias](./d/alicloud_ram_account_alias.md)

- [alicloud_ram_account_aliases](./d/alicloud_ram_account_aliases.md)

- [alicloud_ram_groups](./d/alicloud_ram_groups.md)

- [alicloud_ram_policies](./d/alicloud_ram_policies.md)

- [alicloud_ram_roles](./d/alicloud_ram_roles.md)

- [alicloud_ram_saml_providers](./d/alicloud_ram_saml_providers.md)

- [alicloud_ram_users](./d/alicloud_ram_users.md)

- [alicloud_rds_accounts](./d/alicloud_rds_accounts.md)

- [alicloud_rds_parameter_groups](./d/alicloud_rds_parameter_groups.md)

- [alicloud_regions](./d/alicloud_regions.md)

- [alicloud_resource_manager_accounts](./d/alicloud_resource_manager_accounts.md)

- [alicloud_resource_manager_control_policies](./d/alicloud_resource_manager_control_policies.md)

- [alicloud_resource_manager_control_policy_attachments](./d/alicloud_resource_manager_control_policy_attachments.md)

- [alicloud_resource_manager_folders](./d/alicloud_resource_manager_folders.md)

- [alicloud_resource_manager_handshakes](./d/alicloud_resource_manager_handshakes.md)

- [alicloud_resource_manager_policies](./d/alicloud_resource_manager_policies.md)

- [alicloud_resource_manager_policy_attachments](./d/alicloud_resource_manager_policy_attachments.md)

- [alicloud_resource_manager_policy_versions](./d/alicloud_resource_manager_policy_versions.md)

- [alicloud_resource_manager_resource_directories](./d/alicloud_resource_manager_resource_directories.md)

- [alicloud_resource_manager_resource_groups](./d/alicloud_resource_manager_resource_groups.md)

- [alicloud_resource_manager_resource_shares](./d/alicloud_resource_manager_resource_shares.md)

- [alicloud_resource_manager_roles](./d/alicloud_resource_manager_roles.md)

- [alicloud_resource_manager_shared_resources](./d/alicloud_resource_manager_shared_resources.md)

- [alicloud_resource_manager_shared_targets](./d/alicloud_resource_manager_shared_targets.md)

- [alicloud_ros_change_sets](./d/alicloud_ros_change_sets.md)

- [alicloud_ros_stack_groups](./d/alicloud_ros_stack_groups.md)

- [alicloud_ros_stacks](./d/alicloud_ros_stacks.md)

- [alicloud_ros_templates](./d/alicloud_ros_templates.md)

- [alicloud_route_entries](./d/alicloud_route_entries.md)

- [alicloud_route_tables](./d/alicloud_route_tables.md)

- [alicloud_router_interfaces](./d/alicloud_router_interfaces.md)

- [alicloud_sae_service](./d/alicloud_sae_service.md)

- [alicloud_sag_acls](./d/alicloud_sag_acls.md)

- [alicloud_security_group_rules](./d/alicloud_security_group_rules.md)

- [alicloud_security_groups](./d/alicloud_security_groups.md)

- [alicloud_slb_acls](./d/alicloud_slb_acls.md)

- [alicloud_slb_attachments](./d/alicloud_slb_attachments.md)

- [alicloud_slb_backend_servers](./d/alicloud_slb_backend_servers.md)

- [alicloud_slb_ca_certificates](./d/alicloud_slb_ca_certificates.md)

- [alicloud_slb_domain_extensions](./d/alicloud_slb_domain_extensions.md)

- [alicloud_slb_listeners](./d/alicloud_slb_listeners.md)

- [alicloud_slb_master_slave_server_groups](./d/alicloud_slb_master_slave_server_groups.md)

- [alicloud_slb_rules](./d/alicloud_slb_rules.md)

- [alicloud_slb_server_certificates](./d/alicloud_slb_server_certificates.md)

- [alicloud_slb_server_groups](./d/alicloud_slb_server_groups.md)

- [alicloud_slb_zones](./d/alicloud_slb_zones.md)

- [alicloud_slbs](./d/alicloud_slbs.md)

- [alicloud_snapshots](./d/alicloud_snapshots.md)

- [alicloud_snat_entries](./d/alicloud_snat_entries.md)

- [alicloud_ssl_vpn_client_certs](./d/alicloud_ssl_vpn_client_certs.md)

- [alicloud_ssl_vpn_servers](./d/alicloud_ssl_vpn_servers.md)

- [alicloud_tsdb_instances](./d/alicloud_tsdb_instances.md)

- [alicloud_tsdb_zones](./d/alicloud_tsdb_zones.md)

- [alicloud_vpcs](./d/alicloud_vpcs.md)

- [alicloud_vpn_connections](./d/alicloud_vpn_connections.md)

- [alicloud_vpn_customer_gateways](./d/alicloud_vpn_customer_gateways.md)

- [alicloud_vpn_gateways](./d/alicloud_vpn_gateways.md)

- [alicloud_vs_service](./d/alicloud_vs_service.md)

- [alicloud_vswitches](./d/alicloud_vswitches.md)

- [alicloud_waf_domains](./d/alicloud_waf_domains.md)

- [alicloud_waf_instances](./d/alicloud_waf_instances.md)

- [alicloud_yundun_bastionhost_instances](./d/alicloud_yundun_bastionhost_instances.md)

- [alicloud_yundun_dbaudit_instance](./d/alicloud_yundun_dbaudit_instance.md)

- [alicloud_zones](./d/alicloud_zones.md)


[top](#index)