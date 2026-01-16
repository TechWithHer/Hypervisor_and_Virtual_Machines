## 6️⃣ Hands-on: Your First VM (No shortcuts)

### ✅ Step 1: Install VirtualBox

* Download VirtualBox (Oracle)
* Install Extension Pack (same version)

This is **non-negotiable**.

---

### ✅ Step 2: Download an OS image

Download:

* **Ubuntu Server 22.04 LTS (ISO)**

Why server, not desktop?
👉 DevOps ≠ clicking GUI
👉 Servers run **headless**

---

### ✅ Step 3: Create the VM

In VirtualBox:

* Name: `ubuntu-devops`
* Type: Linux
* Version: Ubuntu (64-bit)

Resources (don’t be greedy):

* RAM: 2 GB
* CPU: 2 cores
* Disk: 20 GB (VDI, dynamically allocated)

---

### ✅ Step 4: Attach ISO & Install

* Attach Ubuntu ISO
* Start VM
* Follow installation:

  * Language: English
  * Install OpenSSH Server ✅ (important)
  * Username/password: remember it

When done → reboot → remove ISO.

🎉 You just created a **real server**.

---

## 7️⃣ Hands-on: Prove it’s isolated

Inside the VM:

```bash
hostname
ip a
df -h
free -m
```

Now run same commands on your host machine.

👉 Different hostname
👉 Different IP
👉 Different disk
👉 Different memory

**This is isolation.**

---

## 8️⃣ SSH into your VM (DevOps-style)

Set VM network to:

* **Bridged** or **NAT with port forwarding**

From your host:

```bash
ssh username@vm_ip
```

Now ask yourself:

> Am I on my laptop or a server?

That confusion is **exactly why VMs matter**.

---

## 9️⃣ Snapshot (DevOps superpower)

In VirtualBox:

* Take Snapshot: `fresh-install`

Now break something intentionally:

```bash
sudo rm -rf /etc/somefile
```

VM broken?
👉 Restore snapshot
👉 Back in 10 seconds

This is **infrastructure safety**.

---

## 🔟 Where VMs fit in DevOps (real world)

| Tool             | Uses VMs? |
| ---------------- | --------- |
| AWS EC2          | Yes       |
| Kubernetes Nodes | Yes       |
| Jenkins agents   | Often     |
| CI/CD runners    | Yes       |
| On-prem servers  | Yes       |

Docker did **not** replace VMs.
Docker **runs on top of VMs** in production.

---

## 11️⃣ Common beginner mistakes (I won’t sugarcoat)

❌ Thinking Docker replaces VMs
❌ Only using GUI, never terminal
❌ Not understanding networking inside VMs
❌ Ignoring snapshots
❌ Treating VMs like toys

Avoid these, you move faster than 70% beginners.

---

## 12️⃣ Your DevOps Practice Tasks (Do this seriously)

### Task 1

* Create **2 Ubuntu VMs**
* Ping each other

### Task 2

* SSH from VM1 → VM2

### Task 3

* Take snapshot
* Install nginx
* Break it
* Restore snapshot

### Task 4

* Check CPU & RAM usage live

```bash
top
htop
```

---

## 13️⃣ What I’ll teach you next (if you want)

You should **not jump randomly**. Correct order:

1. VM Networking (NAT vs Bridged)
2. Linux services inside VM
3. Docker **inside** VM
4. Kubernetes nodes as VMs
5. Cloud mapping (EC2 = VM)

If you want, say:

> “Teach me VM networking like a DevOps engineer, with labs”

And we go deeper 🚀
