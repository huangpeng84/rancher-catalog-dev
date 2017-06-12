# Openstack Kolla Deployment
---

### Purpose
This will install Openstack Mitaka using Kolla on the nodes in your environment. The Openstack services will be managed via Kolla and in the **Infrastructure** -> **Hosts** page, the services will show up in the `Standalone Containers` section.

Once installed, you will have a basic Openstack deployment with the Cirros image and standard VM flavors available to you. 

A good reference for additional information can be found on the [Kolla Quickstart Guide](http://docs.openstack.org/developer/kolla/quickstart.html).

### Pre-Reqs

 * Minimum requirements of 2 Rancher hosts
    * 1 host:
        * 8GB RAM
        * 40GB disk
        * [Host label](http://docs.rancher.com/rancher/latest/en/rancher-ui/infrastructure/hosts/#host-labels) of `openstack=controller` 
    * N hosts:
        * `>= 4GB` RAM
        * 40GB disk
        * [Host label](http://docs.rancher.com/rancher/latest/en/rancher-ui/infrastructure/hosts/#host-labels) of `openstack=compute` 
 * KVM enabled
 * Networking needs to be preconfigured 
 	* You will need 1 interface for the APIs and management, and one for Neutron
 *  On OSes Rancher OS versions < v1.5.0 or Other operating systems
    `/run` needs to be shared on the host
 	* `mount --make-shared /run` 
 	
 		-- or --
 	
 	* For systemd systems
 	
 	```
 	 # Create the drop-in unit directory for docker.service
     $ mkdir -p /etc/systemd/system/docker.service.d
     
	 # Create the drop-in unit file
	 $ tee /etc/systemd/system/docker.service.d/kolla.conf <<-'EOF'
	 [Service]
	 MountFlags=shared
	 EOF
     
	 # Run these commands to reload the daemon
	 $ systemctl daemon-reload
	 $ systemctl restart docker
	```

 * Ensure Libvirt is not running base os

### Basics
 
 * How do I log in to Horizon?
 	* The project is `default`. The username created is `admin` and the password is what was set as Openstack admin password.
 	* If you are unable to log in, on the controller node (i.e. host with label `openstack=controller`, please make sure that in `/etc/kolla/admin-openrc.sh` the `OS_PASSWORD` should be available.
 * How do I set up my networks?
 	* You can use the Horizon UI.
 	* Use the Rancher UI, to **Exec** into the `openstackcontroller` container. Source `/etc/kolla/admin-openrc.sh` and use the Openstack command line tools, (i.e. `neutron`).
