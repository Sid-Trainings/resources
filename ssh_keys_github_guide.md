
# 🔐 Generating and Adding SSH Keys to GitHub

## 📍 Pre-requisites

- Git must be installed: [Install Git](https://git-scm.com/downloads)
- GitHub account logged in

---

## ✅ Steps for Windows

### 1. Open Git Bash  
(You can install Git Bash from [git-scm.com](https://git-scm.com/))

### 2. Generate SSH Key

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

If `ed25519` is not supported, use:

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

> Press **Enter** to accept the default file location. Optionally set a passphrase.

### 3. Start SSH Agent

```bash
eval "$(ssh-agent -s)"
```

### 4. Add SSH Private Key to Agent

```bash
ssh-add ~/.ssh/id_ed25519
```

> Use `id_rsa` if you used RSA method.

### 5. Copy Public Key

```bash
clip < ~/.ssh/id_ed25519.pub
```

> If `clip` doesn’t work, open the file manually from the `.ssh` folder in your user directory.

### 6. Add Key to GitHub

- Go to **GitHub → Settings → SSH and GPG keys**
- Click **New SSH key**
- Paste the copied key
- Give a **title** and save

---

## ✅ Steps for Linux

### 1. Open Terminal

### 2. Generate SSH Key

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

If `ed25519` is unsupported:

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

> Press **Enter** to accept the default path. Set a passphrase if desired.

### 3. Start SSH Agent

```bash
eval "$(ssh-agent -s)"
```

### 4. Add SSH Key to Agent

```bash
ssh-add ~/.ssh/id_ed25519
```

### 5. Copy Public Key

```bash
cat ~/.ssh/id_ed25519.pub
```

> Copy the output manually.

### 6. Add Key to GitHub

- Go to **GitHub → Settings → SSH and GPG keys**
- Click **New SSH key**
- Paste the key
- Save it with a title

---

## 🧪 Test the SSH Connection

```bash
ssh -T git@github.com
```

If successful, you’ll see:

```
Hi username! You've successfully authenticated.
```
