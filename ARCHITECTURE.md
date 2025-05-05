# Proje Mimarisi

```mermaid
flowchart LR
  A[👤 Kullanıcı (Browser)] -->|HTTPS| B[🌐 Angular SPA]
  B -->|HTTPS /api/**| C[Nginx Reverse Proxy]
  C -->|HTTP /api/**| D[🚀 Spring Boot App]
  subgraph JWT_Security ["JWT Auth & Security"]
    D --> E[JwtAuthFilter]
    E --> F[SecurityConfig]
  end
  subgraph Backend_Layers ["Spring Boot Katmanları"]
    F --> G[Controllers]
    G --> H[Services]
    H --> I[Repositories]
    I --> J[(MySQL Database)]
  end
