# How to deal with mdBook

The most essential thing about **mdBook** is that it can be installed via many routes. It can be installed using Cargo, Rust, or from the Ubuntu repositories, which is **not** recommended.

***

### 🧠 How mdBook Is Installed (Brief Reminder)

**mdBook** is best installed via Rust’s package manager:
```bash
cargo install mdbook
```
So, updating = reinstalling the latest version.

### 🚀 Update mdBook (Simple)

Run:

```bash
cargo install mdbook --force
```
### What this does

*  downloads latest mdBook
* rebuilds it
*   replaces existing binary

### 🧪 Check Version

```bash
mdbook --version
OR
mdbook -V
```
### ⚠️ If You Get Weird Behaviour
Sometimes old binaries linger.

Check location:

```bash
which mdbook
```
Usually:

```bash
~/.cargo/bin/mdbook
```

## 🧹 Optional Clean Rebuild (If Something Feels Off)

```bash
cargo uninstall mdbook
cargo install mdbook
```

### ⚡ Faster Updates (Optional Tip)

If you update often:

```bash 
cargo install mdbook --force --locked
```
👉 ensures consistent dependency versions

## ⚙️ What Is Being “Locked”?

Rust projects include a file:
```
Cargo.lock
```
**This file contains:**

*   exact versions of every dependency
*   full dependency tree
*   versions known to work together

Without `--locked`

Cargo does this:


***
## 🧠 Bonus (Useful Later)

Update everything Rust-related:

```bash
rustup update
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTYxMDYzOTY2MywtMTM1OTYzMzUzMV19
-->