Knife vCHS
===============

This is the official Chef Knife plugin VMware's vCloud Hybrid Service (vCHS). This plugin gives knife the ability to create, bootstrap and manage instances on vCHS-based public and private clouds.

Please refer to the [CHANGELOG](CHANGELOG.md) for version history and known issues.

# Installation #

This plugin is distributed as a Ruby Gem. To install it, run:

    $ gem install knife-vchs

If you are using the Chef Development Kit (Chef DK), to install it run:

    $ chef gem install knife-vchs

# Configuration #

In order to communicate with an vCHS API you will need to tell Knife your vCHS API endpoint, your username and password. The easiest way to accomplish this is to create these entries in your `knife.rb` file:

    knife[:vchs_api_url] = 'vchs.example.com'
    knife[:vchs_username] = 'Your vCHS username'
    knife[:vchs_password] = 'Your vCHS password'

If your knife.rb file will be checked into a SCM system (ie readable by others) you may want to read the values from environment variables.

    knife[:vchs_api_url] = "#{ENV['VCHS_AUTH_URL']}"
    knife[:vchs_username] = "#{ENV['VCHS_USERNAME']}"
    knife[:vchs_password] = "#{ENV['VCHS_PASSWORD']}"

## VMware's vCHS ##

If you are using VMware's hosted vCHS the API URL is found by logging into the https://vchs.vmware.com, and clicking on your Dashboard's Virtual Data Center. On the right under "Related Links" click on the "vCloud Director API URL" and copy that value. It should look something like `https://p3v11-vcd.vchs.vmware.com:443/cloud/org/M511664989-4904/` From this we will tak our base API URL `p3v11-vcd.vchs.vmware.com` and get our organization `M511664989-4904` that is appended to our https://vchs.vmware.com login, giving us the values:

    knife[:vchs_api_url] = 'p3v11-vcd.vchs.vmware.com'
    knife[:vchs_username] = 'user@somedomain.com@m511664989-4904'
    knife[:vchs_password] = 'VCHSSECRET'

# knife vchs subcommands #

This plugin provides the following Knife subcommands. Specific command options can be found by invoking the subcommand with a `--help` option.

## knife vchs server create OR knife vchs vm create ##
No "flavor list"

## knife vchs server delete OR knife vchs vm delete ##

## knife vchs server list OR knife vchs vm list ##

## knife vchs image list OR knife vchs template list ##

## knife vchs nat_rules list ##

## knife vchs firewall_rules list ##

## knife vchs networks list ##

## knife vchs public_ips list ##

# License #

Author:: Matt Ray (<matt@getchef.com>)

Author:: Seth Thomas (<sthomas@getchef.com>)

Copyright:: Copyright (c) 2014 Chef Software, Inc.

License:: Apache License, Version 2.0

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
