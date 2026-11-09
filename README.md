# communiNet-freemesh

Descentralized community mesh network and messaging ecosystem

CommuniNet / FreeMeshResilient, Decentralized, and Community-Driven Global Connectivity EcosystemBridging the digital divide globally through decentralized community mesh networks, zero-tariff satellite backhauls, and E2EE local communications.

1. Overview and Project VisionCommuniNet / FreeMesh is an open-source, decentralized connectivity and community ecosystem engineered to eradicate digital isolation in rural, remote, and underserved regions globally. By decoupling access from monopolistic market barriers, the platform provides unhindered, secure, and resilient digital infrastructure where anyone, anywhere, can connect instantly.The ecosystem operates on a dual-layer model:The Infrastructure Layer: Autonomous community gateway nodes leveraging low-earth orbit (LEO) satellite links (3GPP Non-Terrestrial Networks) combined with next-generation local mesh technologies (Wi-Fi 7 / Wi-Fi 6E / Li-Fi).The Application Layer: A sovereign cross-platform mobile application providing end-to-end encrypted peer-to-peer (P2P) messaging, local community forums, and federated social feeds operating completely offline-first via store-and-forward routing.2. Network and System ArchitectureThe logical topology of CommuniNet is structured to maintain absolute operational integrity even during catastrophic wide-area network or satellite link failures. ┌───────────────────────────────────────────────────────────────┐
 │               LEO Satellite Constellation                     │
 │               (3GPP Rel-17/18 NTN Direct-to-Cell)             │
 └──────────────────────────────┬────────────────────────────────┘
                                │ Backhaul (Burst / Dynamic SDN)
 ┌──────────────────────────────▼────────────────────────────────┐
 │             Edge Community Gateway (Open Hardware)            │
 │     [Wi-Fi 6E/7 Access Point] ◄───► [Li-Fi Optical Link]      │
 └──────────────────────────────┬────────────────────────────────┘
                                │ Local Area Distribution
       ┌────────────────────────┼────────────────────────┐
       ▼                        ▼                        ▼
 ┌───────────┐            ┌───────────┐            ┌───────────┐
 │ Mobile Node│◄─BLE Mesh─►│ Mobile Node│◄─Wi-Fi Dir─►│ Mobile Node│
 │  (Client) │            │  (Client) │            │  (Client) │
 └───────────┘            └───────────┘            └───────────┘
Logical Data Flow & AprovisioningGlobal Authentication (W3C DIDs): Users authenticate locally using decentralized identifiers (DIDs) backed by public-key cryptography—eliminating the dependency on centralized telephone numbers or external identity providers.Dynamic Backhaul Routing (SDN): Edge gateways orchestrate internet traffic dynamically, routing packets through available LEO satellite links or local community fiber when present.Store-and-Forward Mesh Propagation: When internet backhaul is offline, nearby mobile nodes leverage Bluetooth Low Energy (BLE) Mesh and Wi-Fi Direct to propagate messages across community hops asynchronously.3. Recommended Technology StackThe project relies on memory-safe, performant, and cross-platform modern standards:LayerTechnologyPurposeMobile FrontendFlutter (Dart)High-performance, cross-platform mobile UI for Android & iOS.Mesh & Network CoreRust (via Flutter FFI / Native plugins)Low-level socket management, BLE/Wi-Fi Direct bindings, and routing protocols.Cryptography & Securitylibsodium (Curve25519, ChaCha20-Poly1305, Ed25519)Implementation of the Signal Protocol for End-to-End Encryption (E2EE) and message signing.Local Database & StorageIsar / SQLCipherEncrypted, ultra-fast NoSQL/SQL storage optimized for offline-first querying.Gateway Edge FirmwareOpenWrt / Linux Kernel (Raspberry Pi CM4 / Rockchip)Edge routing software for community solar-powered nodes.4. Core FeaturesZero-Tariff Universal Access: Seamless onboarding for any user globally with optimized bandwidth usage and zero financial barriers.Resilient Offline-First Messaging: Asynchronous peer-to-peer chat running locally via mesh protocols even when satellite connections drop.Decentralized Community Forums: Local bulletin boards and social feeds secured via cryptographic signatures to prevent tampering or injection of false information.Military-Grade Privacy by Design: Perfect Forward Secrecy (PFS) and Post-Compromise Security through Double Ratchet algorithms.Modular Multi-Link Connectivity: Support for Wi-Fi 7 Multi-Link Operation (MLO) and Li-Fi environments for high-density indoor spaces.5. Planned Repository Folder Structurecommuninet-freemesh/
├── .github/                      # CI/CD workflows, issue templates, and pull request rules
├── docs/                         # Architecture diagrams, whitepapers, and API specifications
├── gateway-firmware/             # Edge router configuration, OpenWrt packages, and SDN scripts
└── mobile-app/                   # Main cross-platform mobile workspace (Flutter)
    ├── pubspec.yaml
    └── lib/
        ├── app/                  # Application configuration, routing, and dependency injection
        ├── core/                 # Shared core utilities (Crypto wrappers, storage adapters, loggers)
        └── features/             # Feature-driven modular architecture
            ├── auth/             # W3C Decentralized Identifiers (DIDs) and key management
            ├── mesh_network/     # BLE and Wi-Fi Direct transport layers and peer discovery
            ├── messaging/        # E2EE chat, store-and-forward queues, and sync engines
            ├── forums/           # Local community boards and cryptographically signed posts
            └── dashboard/        # Node health, satellite link metrics, and network topology view
6. Roadmap & Development MilestonesPhase 1: Core P2P Messaging & Local Mesh (Current)[ ] Initialize Flutter multiplatform project skeleton.[ ] Implement local peer discovery using BLE and Wi-Fi Direct abstractions.[ ] Build offline local database with Isar/SQLCipher.[ ] Develop asynchronous store-and-forward queue mechanism.Phase 2: Cryptographic Rigor & Security Layer[ ] Integrate libsodium bindings for keypair generation.[ ] Implement Signal Protocol (Double Ratchet) for direct chats.[ ] Establish W3C Decentralized Identifiers (DIDs) for anonymous, secure local authentication.[ ] Conduct threat modeling and penetration testing against Sybil attacks.Phase 3: Hardware Edge Gateway & Satellite Integration[ ] Package OpenWrt edge routing scripts for Raspberry Pi CM4 / Rockchip hardware.[ ] Implement 3GPP NTN interface bindings for LEO satellite backhaul simulation.[ ] Optimize solar-power management modules (12V/24V telemetry).Phase 4: Institutional Pilots & Ecosystem Scaling[ ] Release first municipal field test with 50 deployed community nodes.[ ] Establish B2G framework templates for public-private partnerships.[ ] Open open-source community governance and developer grant programs.ContributingWe welcome contributors, researchers, protocol engineers, and social technologists passionate about digital sovereignty. Please read our CONTRIBUTING.md before submitting pull requests.LicenseDistributed under the MIT License. See LICENSE for more information.
