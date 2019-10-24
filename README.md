[![Build Status](https://travis-ci.org/mvilrokx/new_relic_deployment_marker.svg?branch=master)](https://travis-ci.org/mvilrokx/new_relic_deployment_marker)

# Ansible Role: new_relic_deployment_marker

Create [Deployment Markers in New Relic](https://docs.newrelic.com/docs/apm/new-relic-apm/maintenance/record-monitor-deployments).

## Requirements

none

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    new_relic_api_base_url: "https://api.newrelic.com/v2/"

The New Relic API base URL, DO NOT CHANGE.

    new_relic_api_timeout: 10

A timeout (in seconds) for the calls to the New Relic APIs used by this role.

    revision: ""

The `revision` parameter for the New Relic Deployment Marker API.

    changelog: ""

The `changelog` parameter for the New Relic Deployment Marker API.

    description: ""

The `description` parameter for the New Relic Deployment Marker API.

    {{ new_relic_api_key }}

The New Relic API key, provided by New Relic (Account Settings > API Keys)

    {{ inventory_hostname }}

This role uses the {{ inventory_hostname }} to find the application id

## Dependencies

You obviously need a New Relic Account and an Application that New Relic is monitoring.

## Example Playbook

    - hosts: servers
      tasks:
        - include_role:
            name: new_relic_deployment_marker
          vars:
            revision: "1.0"
            changelog: "New release"

## License

BSD

## Author Information

This role was created in 2019 by [Mark Vilrokx](https://www.vilrokx.com/).
