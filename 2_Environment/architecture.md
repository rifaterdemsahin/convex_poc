# Architecture — Convex.dev PoC

## System Overview

```mermaid
graph TB
    subgraph Client["Client (Browser)"]
        UI[React UI]
        SDK[Convex React SDK]
        UI -->|useQuery / useMutation| SDK
    end

    subgraph Convex["Convex Cloud"]
        RT[Real-time Engine]
        DB[(Convex DB)]
        FN[Functions Runtime]
        SDK -->|WebSocket| RT
        RT -->|Reactive push| SDK
        RT --> FN
        FN --> DB
    end

    subgraph Azure["Azure"]
        KV[Key Vault\ndp-kv-deliverypilot]
    end

    subgraph GitHub["GitHub"]
        Pages[GitHub Pages\nStatic Site]
        Actions[GitHub Actions]
        Actions -->|Deploy| Pages
        Actions -->|Fetch secrets| KV
    end
```

## Data Flow

```mermaid
sequenceDiagram
    participant C as Client
    participant R as Convex Runtime
    participant D as Convex DB

    C->>R: useQuery("listMessages")
    R->>D: SELECT * FROM messages ORDER BY _creationTime
    D-->>R: [{text, author, _id}]
    R-->>C: Initial result

    Note over C,D: Real-time subscription active

    C->>R: useMutation("sendMessage")
    R->>D: INSERT INTO messages
    D-->>R: Committed
    R-->>C: Push update to all subscribers
```

## Key Components

| Component | Technology | Purpose |
|-----------|-----------|---------|
| Frontend | React + Vite | UI layer |
| Real-time layer | Convex React SDK | Query subscriptions + mutations |
| Backend functions | Convex (TypeScript) | Business logic, data access |
| Database | Convex DB | ACID-compliant document store |
| Secrets | Azure Key Vault | Deploy key + env vars |
| Hosting | GitHub Pages | Static site delivery |
