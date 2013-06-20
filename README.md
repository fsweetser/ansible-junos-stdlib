DESCRIPTION
===========

__EXPERIMENTAL!!__  Junos modules written to work with [Anisble 1.2](http://www.ansibleworks.com).  This repo contains the modules, `library` directory, as well as playbooks, `junos` directory, and reusable tasks, `tasks` directory.

These modules use the `connection: local` method to establish a NETCONF connection to the remote Junos devices.  No additional software is required to be installed on the Junos device.

USAGE
=====

  Refer to the ansible-junos-demo repository for sample demonstration use-case to install Junos software, template build configurations, and initialize devices with configs.
  
MODULES
=======

  * `junos_get_facts` - returns a hash structure of "facts" about the device.  These include the hardware model, serial-number, and current Junos OS version
  
  * `junos_install_os` - IDEMPOTENT - will install designated Junos OS release if it is not already installed.  This module also supports an *audit* mode to check the existing release againt the designated release

  * `junos_install_config` - used to install an entire Junos configuration ("override" mode) or just a configuration snippet ("merge" mode).  Configurations can be either in "set" format, "text" format, or "xml" format.

  * `junos_rescue` - used to reload the saved "rescue configuration" file.  This assumes that a rescue configuration file has be previously saved 
  
  For documentation on each of the above modules, please refer directly to the source code

DEPENDENCIES
============

  The modules are currently written in Ruby, as we had a lot of Ruby gems already written for Junos automation.  We have not started a Python port, but if you're interested in helping out on that effort, please let me know.  You will need the following:
  
  * Ruby 1.9.3
  * Gem: [netconf](https://github.com/Juniper-Workflow/net-netconf)
  * Gem: [junos-ez-stdlib](https://github.com/jeremyschulman/ruby-junos-ez-stdlib)

LICENSE
=======
  BSD-2
  
