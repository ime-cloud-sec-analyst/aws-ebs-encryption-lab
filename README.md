# aws-ebs-encryption-lab
AWS lab project demonstrating how to create, encrypt, attach, mount, and persist an EBS volume using KMS and /etc/fstab.
# AWS EBS Encryption and Mounting Lab

This repository contains the screenshots, setup steps, and configuration details for an AWS lab exercise focused on encrypting and attaching Amazon EBS volumes to an EC2 instance. It demonstrates how to persist the mount using the `/etc/fstab` file.

---

## 🧪 Lab Objectives

- Create and attach an **encrypted EBS volume** using **KMS**
- Format the volume with a filesystem (`ext4`)
- Mount the volume to a specific directory (`/mnt/myvolume`)
- Make the mount persistent using the **UUID** in `/etc/fstab`
- Verify that the volume is correctly mounted

---

## 📁 Files Included

- 📷 Screenshots documenting each lab step
- 📄 UUID and `blkid` command outputs
- 📄 `/etc/fstab` configuration
- 📄 Terminal outputs for `df -h`, `lsblk`, `mount`, and `blkid`

---

## 🧩 Key Commands Used

```bash
sudo mkfs -t ext4 /dev/xvdf
sudo mkdir /mnt/myvolume
sudo mount /dev/xvdf /mnt/myvolume
df -h
sudo blkid
sudo cp /etc/fstab /etc/fstab.bak
sudo nano /etc/fstab
sudo mount -a
✅ Verification
Volume is mounted at /mnt/myvolume

Mount persists after reboot due to correct /etc/fstab entry using UUID

Verified with df -h and lsblk

📌 Notes
Volume was created and encrypted using a KMS key.

AWS region: us-west-2

Linux kernel may rename devices to /dev/xvdf internally.

🧠 Author
Ime Ben (ime-cloud-sec-analyst)
Cloud Security & Compliance 
GitHub: @ime-cloud-sec-analyst
