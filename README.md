# Openstack Development Lab
==========

## Overview

This allows for setting up a development lab environment using
[Vagrant](http://www.vagrantup.com/downloads.html).

## Lab Description

Vagrant sets up following  nodes:
 - Openstack Grizzly all-in-one node on Ubuntu 12.04;
 - Openstack Icehouse all-in-one node on Ubuntu 14.04;
 - Openstack Juno all-in-one node on Ubuntu 14.04;
 - Openstack Liberty all-in-one node on Ubuntu 14.04;
 - NFS server node on Ubuntu 14.04

## Configuration

Configuration is done through modifying `config.ini`. Most recent configurable
options:

## Prerequisites

 - Vagrant, version >= 1.6
 - Virtualbox

## Setup

 1. Make sure you have all prerequisites installed;
 2. Clone [CloudFerry](https://github.com/MirantisWorkloadMobility/CloudFerry)
    repository and navigate to `cloudferry_devlab` folder
    ```
    git clone https://github.com/MirantisWorkloadMobility/CloudFerry.git
    cd CloudFerry/cloudferry_devlab
    ```
 3. Configure according to your needs (see Configuration)
 4. Start vagrant
    ```
    vagrant up
    ```
    or
    ```
    vagrant up grizzly juno
    ```
 5. You also can start minimum development environment by running:
    ```
    vagrant up grizzly icehouse nfs
    ```

## Common Vagrant use-cases

 1. Check current VMs state (whether it's up, down and so on)
   - `vagrant status`
 2. SSH
   - `vagrant ssh <vm name>`
   - `<vm name>` is one of grizzly, icehouse, juno or nfs
 3. SSH configuration used for each VM:
   - `vagrant ssh-config <vm name>`
 4. If something went wrong and you cannot ssh with keypairs, all the VMs have
    following users:
   - Username: vagrant
   - Password: vagrant
 5. `vagrant` user is added to paswordless sudoers, so you can easily become
    root:
   - `sudo su -`

