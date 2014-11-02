puppet-zabbix-reports
---------------------

**Description**

A Puppet report processor for sending metrics to a [Zabbix](http://www.zabbix.org/)
server via zabbix trapper protocol.

**Installation and usage**

* Install `puppet-zabbix-reports` as a module in your puppet master's module
  path (defaults to `/etc/puppet/puppet.conf`).

* On master run `puppet plugin download`, to sync files to `lib`
  (e.g. `/var/lib/puppet/lib`)

* Update the `zabbix_host` and `zabbix_port` variables in `zabbix.yaml`.
  Copy `zabbix.yaml` to puppet config directory. An example file is included.

* Configure zabbix master to use the `zabbix` report:

```ini
[master]
    reports = store, zabbix
```

* Enable `pluginsync` and `report` on your agents:
  your `puppet.conf`.

```ini
[main]
  report     = true
  pluginsync = true
```

* Import the zabbix template in `zabbix-template.xml`.

* Link the template to hosts managed by puppet. Note that the
  host name in zabbix will need to match the puppet certname

**TODO**

* actually create the zabbix template
* write some unit tests (really?)
* check on real environment
* submit the module to PuppetForge

**License**

    Author:: Alex Simenduev (<shamil.si@gmail.com>)
    Copyright:: Copyright (c) 2014 Alex Simenduev
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