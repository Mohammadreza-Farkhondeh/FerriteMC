# FerriteMC

**FerriteMC** is a fast, modular Minecraft server written in Rust—designed for customizability, performance, and clean architecture. It supports powerful **Lua scripting**, giving you full control over world generation, gameplay rules, and server behavior without recompiling.

> 🧠 Built for developers, modders, and tinkerers who care about code, not graphics.

---

## ✨ Features

- ⚡ **Rust Backend** — high-performance, safe, and multi-threaded
- 🌍 **Lua Scripting** — define world generation, server config, and gameplay logic via easy-to-write scripts
- 🔁 **Hot Reloading** — update scripts without restarting the server
- 🧩 **Pluggable Design** — clear API boundaries between engine and logic
- 📦 **Lightweight** — minimal dependencies, fast startup, low memory usage

---

## 🚀 Getting Started

### 1. Clone the Project

```bash
git clone https://github.com/MohammadrezaFarkhondeh/ferritemc.git
cd ferritemc
````

### 2. Build the Server

```bash
cargo build --release
```

### 3. Run It

```bash
cargo run
```

By default, it will load `scripts/world.lua` and generate chunks from your Lua-defined logic.

---

## 📜 Lua Scripting

Write your logic in `scripts/` using simple Lua functions.

### Example: `world.lua`

```lua
function generate_chunk(x, z)
    local chunk = {}
    for i = 0, 15 do
        for j = 0, 15 do
            chunk[(i * 16) + j] = {
                height = 64,
                block = "grass"
            }
        end
    end
    return chunk
end
```

### Example: `config.lua`

```lua
return {
    max_players = 20,
    motd = "Welcome to FerriteMC!",
    allow_flight = true
}
```

The Rust engine automatically loads and applies these on boot.

---

## 🧪 Development Goals

* [ ] Core Minecraft protocol support (login, chunks, movement)
* [ ] Lua hooks for events (on\_join, on\_block\_place, etc.)
* [ ] Plugin system for loading Lua modules
* [ ] Optional file-based persistent worlds
* [ ] Built-in metrics & debugging tools

---

## 🛠 Built With

* [Rust](https://www.rust-lang.org/) – memory-safe, high-performance systems language
* [mlua](https://crates.io/crates/mlua) – safe and fast Lua embedding for Rust
* [tokio](https://tokio.rs/) – async runtime for network handling
* [serde](https://serde.rs/) – efficient data serialization

---

## 🎯 Vision

**FerriteMC** is not just a Minecraft clone—it’s a sandbox for server-side innovation.
Build new worlds, mechanics, or even game modes with the precision of Rust and the agility of Lua.

---

## 📄 License

MIT License. See `LICENSE` for details.

---

## 👋 Contributing

Pull requests and discussions welcome! If you’d like to help build core systems, extend Lua scripting, or improve performance, jump into `src/` or open an issue.

