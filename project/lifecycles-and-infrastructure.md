---
description: Understand the Remède's structure.
---

# 👣 Lifecycles and infrastructure

{% hint style="info" %}
These schemas are a bit old and hard to understand, but they can help you to understand how Remède is working.
{% endhint %}

## Application working schema

This schema shows how the mobile application (with the dictionary downloaded) is retrieving the data.

```mermaid
graph LR
    subgraph "Application Side"
        subgraph "Database"
            DB[(Database)] --> Index
            DB --> Main
            DB --> Rimes
            subgraph Index["Search index (wordlist)"]

            end
            subgraph Main["Default table (dictionary)"]

            end
            subgraph Rimes["Rimes table (rimes)"]

            end
        end
        Main <-.-> A[WebView]
        Index <-.-> A[WebView]
        Rimes <-.-> A[WebView]
    end
    subgraph "Filesystem" 
        DFB[[DatabaseFile]] --> DB
    end
```



## Infrastructure schema

This schema shows which extern services are used through their API by the mobile application.

```mermaid
graph LR
    subgraph "`fa:fa-user User side`"
        J[(Database)] <-.-> A((User))
    end
    subgraph "`fa:fa-server Server side`"
        subgraph fa:fa-circle-nodes Proxy
            A((User)) --> B([Load Balancer])
        end
        subgraph fa:fa-memory Dedicated VM
            B --> C[API]
            B --> D[Ionic Web]
        end
        subgraph docker["`fa:fa-docker Dedicated Docker Server`"]
            B --> G[TTS service]
            B --> H[Corrector service]
        end
        subgraph fa:fa-folder Filesystem
            C --> E[(Database)]
            E --> F[JSON]
        end
    end
```

## Application requests schema

Schemas showing how and when Remède make requests.

### When database is not downloaded

```mermaid
sequenceDiagram
    title Interaction schema with only online Client (database not downloaded)
    box Client
    participant Frontend
    end
    box Server
    participant API
    participant Memory
    participant Filesystem
    end
    API->>Filesystem: Collecting JSON files
    Filesystem-->>API: 
    API-->>Memory: 
    API->>Filesystem: Generating sheets objects
    Filesystem-->>API: 
    API-->>Memory: 
    Note over Frontend,API: Fetching a word
    Frontend->>+API: Can I get word `remède` ?
    API-->>Memory: 
    Memory-->>API: 
    API-->>-Frontend: {[...]}


    Note over Frontend,API: Fetching a sheet
    Frontend->>+API: Can I get sheets ?
    API->>Memory: Get sheet
    Memory-->>API: 
    API->>-Frontend: {[...]}
```



### When database is downloaded

```mermaid
sequenceDiagram
    title Interaction schema with database downloaded on the client filesystem
    box Client
    participant Files as Filesystem
    participant Frontend
    participant Database
    end
    box Server
    participant API
    participant Memory
    participant Filesystem
    end
    Frontend->>Files: Read database
    Files-->>Database: 
    API->>Filesystem: Collecting JSON files
    Filesystem-->>API: 
    API-->>Memory: 
    API->>Filesystem: Generating sheets objects
    Filesystem-->>API: 
    API-->>Memory: 
    Note over Frontend,Database: Fetching a word
    Frontend->>Database: Can I get word `remède` ?
    Database-->>Frontend: 


    Note over Frontend,API: Fetching a sheet
    Frontend->>+API: Can I get sheets ?
    API->>Memory: Get sheet
    Memory-->>API: 
    API->>-Frontend: {[...]}

```



_Here, we can see that sheets can only be fetched with an internet connection. The same goes for the word of the day_
