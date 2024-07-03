# Docker Network
- Docker networking enables communication between Docker containers
  ## types of network
  - bridge
  - host
  - none
  - overlay
 
- Bridge Network: Default network created automatically when Docker is installed. Containers on a bridge network can communicate with each other using IP addresses. Containers can be exposed to the outside world via port mappings.

- Host Network: Containers share the host's network stack, bypassing Docker's network abstraction. This can improve performance but may introduce port conflicts if multiple containers use the same ports.

- Overlay Network: Used for connecting multiple Docker daemons together across multiple hosts. Containers on an overlay network can communicate securely across hosts.

- Macvlan Network: Assigns a MAC address to each container's network interface, making containers appear as physical devices on the network. This allows containers to be directly accessible on the network.

- None Network: Removes networking from the container, meaning the container has no network interfaces. Useful in scenarios where networking is not needed.  
