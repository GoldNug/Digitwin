This file contains documentation for creating a simulated Ruckus CLI
## Creating a simulated CLI
We initially create a CLI with 2 defined access points, 1 online and 1 offline to show contrast. The information provided will include the name, IP Address, Status, Connected Clients, and Power Consumption of said AP
In a selected working directory of choice, first create a nano script
```nano <filename>.sh```

Create the CLI environment and define the specifications of the desired simulated network, with what each command will display
The current version of the simulated CLI has 1 online AP with a randomly generated client and power consumption value, and other function following the typical Ruckus CLI output.
```
#!/bin/bash
echo "Welcome to Ruckus CLI (Simulated)"
while true; do
  read -p "> " cmd
  case $cmd in

    "get ap-list")
      # Generate random values for AP-01
      clients=$((RANDOM % 21 + 5))    # Random clients: 5–25
      txpower=$((RANDOM % 11 + 10))   # Random TX power: 10–20 dBm

      echo -e "AP Name\tIP Address\tStatus\tClients\tTX Power"
      echo -e "AP-01\t10.0.1.5\tOnline\t$clients\t${txpower} dBm"
      echo -e "AP-02\t10.0.1.6\tOffline\t0\t-"
      ;;

    "get wlan-radio AP-01")
      echo "AP Name: AP-01"
      echo "2.4GHz - Channel: 6, Power: 17 dBm, Bandwidth: 20MHz"
      echo "5GHz   - Channel: 149, Power: 20 dBm, Bandwidth: 40MHz"
      echo "EIRP (computed): 20.8 dBm"
      ;;

    "get traffic-ap AP-01")
      uplink=$((RANDOM % 90 + 10))   # 10 to 99 Mbps
      downlink=$((RANDOM % 200 + 50)) # 50 to 249 Mbps
      echo "AP Name: AP-01"
      echo "Uplink: ${uplink}.0 Mbps"
      echo "Downlink: ${downlink}.0 Mbps"
      echo "Peak Clients: $clients"
      ;;

    "exit")
      break
      ;;

    *)
      echo "Unknown command"
      ;;
  esac
done
```

Turn the script into an executable file
```
chmod +x fake-cli.sh
./fake-cli.sh
```

Test the functionality of the implemented commands
```
get ap-list
get wlan-radio AP-01
get traffic-ap AP-01
```
An indicator of a successfully simulated CLI would show [here](https://github.com/GoldNug/Digitwin/blob/main/Results_Simulation/CLI_simulated.png)
In a real environment, the functions would not need to be user-defined, as the vendor (ruckus) would already provide the information and commands
