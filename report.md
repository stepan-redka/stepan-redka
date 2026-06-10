# Report for Task 1: Resume Repository Setup

---

## 1. Repository Creation

 Created new repository on GitHub: [stepan-redka/resume](https://github.com/stepan-redka/resume)

---

## 2. Repository Cloning & SSH Configuration

### Option A: HTTPS Clone
```bash
git clone https://github.com/stepan-redka/resume.git
```

### Option B: SSH Clone (Implemented)

#### Step 1: Generate SSH Key
```bash
ssh-keygen -t ed25519 -C "stepanredka17@gmail.com"
```

**Results:**
- Key location: `/home/stepan/.ssh/id_ed25519`
- Public key fingerprint: `SHA256:0nDzulexGRaj9yvSJIq6s+ub0ZhzIr11HPYqYWPvXi4`
- Public key content (truncated for safety):
  ```
  ssh-ed25519 AAAAC3KGmeT9BXqMj4Lw896K/twqYF4i2ejBxyAgVlEmS0fYG stepanredka17@gmail.com
  ```

#### Step 2: Start SSH Agent
```bash
eval "$(ssh-agent -s)"
```

**Output:**
```
Agent pid 2242042
```

#### Step 3: Add SSH Key to Agent
```bash
ssh-add ~/.ssh/id_ed25519
```

#### Step 4: Add public key on GitHub:
 - GitHub → Settings → SSH and GPG keys
 - Copy and paste ```id_ed25519.pub``` content.

**Output:**
```
Identity added: /home/stepan/.ssh/id_ed25519 (stepanredka17@gmail.com)
```

#### Step 4: Verify GitHub SSH Connection
```bash
ssh -T git@github.com
```

**Output:**
```
Hi stepan-redka! You've successfully authenticated, but GitHub does not provide shell access.
```
 SSH authentication successful

#### Step 5: Clone Repository via SSH
```bash
git clone git@github.com:stepan-redka/resume.git
```

**Output:**
```
Cloning into 'resume'...
warning: You appear to have cloned an empty repository.
```

#### Step 6: Initialize Repository with Content
```bash
cd resume
echo "<h1>My Resume</h1>" > index.html
git add .
git commit -m "Initial resume page"
git push origin main
```

**Results:**
-  Created `index.html` with initial content
-  Initial commit 
-  Pushed to `main` branch on origin

---

## Summary

| Task | Status | Details |
|------|--------|---------|
| GitHub Repository |  Complete | `stepan-redka/resume` created |
| SSH Setup |  Complete | ED25519 key configured & verified |
| Repository Clone |  Complete | Cloned via SSH |
| Initial Content |  Complete | `index.html` added & pushed 