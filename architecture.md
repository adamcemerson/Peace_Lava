```mermaid
flowchart TB
    subgraph systemContext["Local Machine"]
        subgraph vm["UTM"]
            kaliLinux["Kali Linux (Attacker)"]
            webapp["Juice Shop (Target)" on RHEL]
        end
    end

    kaliLinux --> webapp
