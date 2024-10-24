# OAI gNb

The `aether-oai` repository allows OAI RAN (both physical and simulated) to work with the Aether core using Docker.
It has been tested in simulation mode and with USRP X310 as the RAN hardware.

To download the 'aether-oai' repository, use the following command:
```
git clone https://github.com/opennetworkinglab/aether-oai.git
```

## Step-by-Step Installation
To install oai-gNb, follow these steps:

1. Configure the network for oai-gNb:
   - Set the "data_iface" parameter to the network interface name of the machine.
   - Set "network.name" to the name of the Docker network to be created.
   - Set "network.bridge.name" to the name of the interface to be created.
   - Set "subnet", which should correspond to the "ran_subnet" of 5g-core or the machine's subnet.
   - run `oai-router-install` to create the network.
      - To remove the network, run `oai-router-remove`.
3. Start the OAI-gNb Docker containers:
   - Set the container image "gnb_image" for gNb.
   - Set "simulation" to true to run in simulation mode.
   - Set "conf_file" path for coresponding conf file for gNb i.e for simulation/physical.
   - Set "ip" for gNb container, it should in same subnet as network.
   - Set "core.amf.ip" with IP address of Aether core.
   - Start docker container using `make oai-gNb-install`.
      - To stop the gNb, run `make oai-gNb-stop`.  

### One-Step Installation
To install OAI gNb in one go, run `make aether-oai-gNb-install`.

### Uninstall
To uninstall OAI gNb, run `make aether-oai-gNb-uninstall`.
