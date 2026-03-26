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

**Without `--locked`**

**Cargo does this:**

```
Cargo.toml → resolve dependencies → pick latest compatible versions
```

**👉 It may choose:**

*   newer minor versions
*   newer patch versions
*   this will be a bummer

## With `--locked`

Cargo does this instead:

```
Cargo.lock → use EXACT versions → no changes allowed
```
👉 No upgrades  
👉 No re-resolution  
👉 No surprises

## 🧪 Example (Concrete)

Let’s say mdBook depends on:

```TOML
some-crate = "1.2"
```
### Without `--locked`

Cargo might install:

```
some-crate 1.2.7   (latest compatible)
```

### With `--locked`

Cargo installs:

```
some-crate 1.2.3   (exact version in Cargo.lock)
```
## 🎯 Why This Matters

### ✔ With `--locked`

*  reproducible builds
*   exactly what the author tested
*   fewer “it broke for no reason” moments

### ❌ Without it

*   you may get newer dependencies
*   occasionally introduces:
    *   subtle bugs
    *   build failures
    *   behaviour changes

# ☕ Simple Analogy

Without `--locked`:

> “Give me something compatible”

With `--locked`:

> “Give me exactly what the author used”

## 🧠 So Why Did I Suggest It?

Because for tools like mdBook:

-   you don’t need bleeding-edge dependency updates
-   you want stability
-   you want predictability

***
## 🧠 Bonus (Useful Later)

Update everything Rust-related:

```bash
rustup update
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc0MTIwMzA5MywtMTM1OTYzMzUzMV19
-->