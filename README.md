# IPAMLite

## Command Line Operation
```
  IP Address Manager (Lite)
  Example usage:
  $ cd IPAMLite
  $ chmod +x ipam
  $ ./ipam
  
  $ curl -X POST -H "Content-type: application/json" -d "{\"ip\" : \"192.168.1.5\", \"subnet\" : \"24\"}" "127.0.0.1:5000/specific_lease"
  $ curl -X POST -H "Content-type: application/json" -d "{\"network\" : \"192.168.1.0\", \"subnet\" : \"24\"}" "127.0.0.1:5000/sequential_lease"
  $ curl -X POST -H "Content-type: application/json" -d "{\"ip\" : \"192.168.1.5\", \"subnet\" : \"24\"}" "127.0.0.1:5000/release"
  $ curl 127.0.0.1:5000/database

  Currently supported API calls:
    - /specific_lease - HTTP POST, adds a specified IP address to the database
      - Takes: ip, subnet
    - /sequential_lease - HTTP POST, adds the next available IP address in the subnet to the database 
      - Takes: network, subnet
    - /release - HTTP POST, release an IP address from the database
      - Takes: ip, subnet
    - /database - HTTP GET, returns the IP address database
```