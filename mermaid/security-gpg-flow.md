# GPG Key Migration & Portable Setup

Here is a visual representation of your GPG key migration and the current portable setup using a Mermaid flowchart. 

```mermaid
flowchart TD
    %% Define Styles
    classDef laptop fill:#e3f2fd,stroke:#1565c0,stroke-width:2px,color:#000
    classDef yubikey fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px,color:#000
    classDef key fill:#fff8e1,stroke:#f57f17,stroke-width:2px,color:#000
    classDef github fill:#f5f5f5,stroke:#424242,stroke-width:2px,color:#000
    classDef settings fill:#ffffff,stroke:#757575,stroke-width:2px,color:#000,stroke-dasharray: 5 5
    classDef git fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px,color:#000

    subgraph Past [Past State]
        Lenovo["💻 Lenovo Laptop<br>(Ubuntu 24)"]:::laptop
    end
    
    subgraph Current [Current Portable Setup]
        YubiKey["🔑 YubiKey<br>(Hardware Token)"]:::yubikey
        
        GPGKey["<b>GPG Key Data</b><br>Type: RSA 4096<br>Key ID: ****54B44<br>Subkeys: ****A3C8B"]:::key
        
        WorkLaptop["💻 Work Laptop<br>(Windows 11 Enterprise + WSL2)"]:::laptop
        GitSigning["<b>Git</b><br>Commit Signing on the go"]:::git
    end
    
    subgraph Cloud [Remote]
        GitHub["☁️ GitHub.com"]:::github
        GitHubSettings["<b>GitHub Settings</b><br>Unchanged (Key ID remains the same)"]:::settings
    end
    
    %% Relationships
    Lenovo -. "1. Moved key" .-> YubiKey
    YubiKey --- GPGKey
    
    WorkLaptop --- GitSigning
    GitSigning == "2. Requests signature" ==> YubiKey
    
    WorkLaptop -- "3. Pushes signed commits" --> GitHub
    GitHub --- GitHubSettings
```

> [!TIP]
> **Using this in Draw.io**
> You can easily import this exact diagram into Draw.io by copying the Mermaid code block above and in Draw.io going to:
> **Arrange > Insert > Advanced > Mermaid...**
