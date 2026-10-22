# 🌲 Forever Tree

> **"Store your words for eternity. Never altered. Never deleted."**

[![Go Version](https://img.shields.io/badge/Go-1.22+-00ADD8?style=flat&logo=go)](https://go.dev/)
[![Status](https://img.shields.io/badge/status-active_development-emerald?style=flat)](#)
[![Design](https://img.shields.io/badge/architecture-append--only-blueviolet?style=flat)](#)

---

## ✦ Vision

**Forever Tree** is an immutable, append-only message vault built in Go. 

Just like growth rings etched into an ancient tree, every message inscribed into Forever Tree becomes an unalterable part of its permanent history. Once a message is committed, it cannot be edited, rolled back, or erased—creating a tamper-evident chronicle of digital memories, records, and commitments meant to endure indefinitely.

---

## 🏛 Core Tenets

* **Permanence by Design**  
  No `DELETE`, no `UPDATE`. The storage engine strictly forbids destruction and in-place mutation.

* **Append-Only Merkle Lineage**  
  Every message is anchored as a leaf or node in a cryptographic tree structure, providing verifiable proof of inclusion and timestamps.

* **Tamper-Evident History**  
  Any attempt to rewrite the past invalidates downstream cryptographic hashes, making corruption immediately detectable.

* **High Performance & Resilience**  
  Crafted in pure Go with minimal dependencies, focused on rock-solid concurrency, durability, and single-binary deployment.

---

## 🛠 Technology Stack

| Layer | Technology | Purpose |
| :--- | :--- | :--- |
| **Language** | [Go (Golang)](https://go.dev/) | Concurrency, static compilation, memory safety & performance |
| **Storage Paradigm** | Append-Only Log & Merkle Tree | Immutable state progression and tamper resistance |
| **Integrity** | Cryptographic Hashing (SHA-256 / BLAKE3) | Content-addressable referencing and proof-of-history |
| **Interface** | CLI & HTTP/gRPC API | Clean interaction for writers and readers |

---

## 🌳 Architectural Concept

```
                      [ Root Hash ]
                         /     \
                   [ Branch ]   [ Branch ]
                    /      \     /      \
                 [Leaf]  [Leaf] [Leaf]  [Leaf]
                  Msg 1   Msg 2  Msg 3   ... (Forever)
```

1. **Ingest**: A message is accepted and assigned a cryptographic digest and timestamp.
2. **Anchor**: The entry is appended to the persistent log and folded into the immutable tree.
3. **Verify**: Readers can query any message by hash or index along with an audit proof guaranteeing it has remained untouched since creation.

---

## 🚀 Quick Start

### Prerequisites

- [Go](https://go.dev/doc/install) 1.22 or higher

### Running the Project

```bash
# Clone the repository
git clone https://github.com/your-username/forever-tree.git
cd forever-tree

# Run the entry point
go run main.go
```

---

## 🗺 Roadmap

- [ ] Core append-only log engine with disk persistence
- [ ] Merkle Tree hashing and audit proof generation
- [ ] CLI tool for instant message anchoring and verification
- [ ] Lightweight REST/gRPC service for remote commits
- [ ] Distributed replication and cold archival support

---

## 📜 License

Distributed under the MIT License. See `LICENSE` for more information.
