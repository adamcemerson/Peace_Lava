```mermaid
flowchart TB
    subgraph systemContext["Local Machine"]
        subgraph vm["VirtualBox"]
            kaliLinux["Kali Linux (Attacker)"]
            webapp["Juice Shop (Target)"]
        end
    end

    kaliLinux --> webapp
