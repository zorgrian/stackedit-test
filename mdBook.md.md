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
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5MzY2MjE3MzFdfQ==
-->