Here’s a complete and organized set of notes for your **Filesystems & Disks** topic, covering all the points you mentioned. I’ve broken it down logically so it’s easy to study for finals:

---

## **1. Devices**

Linux distinguishes between **block** and **character** devices.

### **Block Devices**

* Devices that read/write data in fixed-size blocks.
* Can be randomly accessed.
* Examples: SSD, HDD, NVMe drives, CDs, USB drives.
* Usually appear under `/dev/sd*` (HDD/SSD), `/dev/nvme*` (NVMe).

### **Character Devices**

* Devices that read/write data as a stream of bytes.
* Sequential access only.
* Examples:

  * `/dev/null` → discards all input, outputs nothing.
  * `/dev/zero` → generates infinite zeros.
  * `/dev/random` → generates random bytes.

---

## **2. Partition Tables & Partitions**

A **partition table** organizes disk storage into partitions.

### **MBR (Master Boot Record)**

* Legacy system, older standard.
* Max 4 primary partitions (or 3 primary + 1 extended with multiple logical partitions).
* Supports disks up to 2 TB.
* Stores bootloader in the first sector (512 bytes).

### **GPT (GUID Partition Table)**

* Modern replacement for MBR.
* Supports large disks (>2 TB) and many partitions (up to 128 in Linux/Windows by default).
* Stores multiple copies of partition table for redundancy.
* Required for UEFI boot.

### **Tools**

* `fdisk` → traditional MBR disk management.
* `gdisk` → GPT partition management.
* `parted` → advanced partition management, supports both MBR and GPT.

---

## **3. Filesystems**

A **filesystem** organizes data on a storage device.

### **Standard Defaults**

| OS      | Default Filesystem |
| ------- | ------------------ |
| Windows | NTFS               |
| Linux   | ext4               |
| macOS   | APFS               |

### **Key Concepts**

* **Compatibility:** Some filesystems work only on certain OSes (e.g., NTFS is readable on Linux but write support requires extra drivers).
* **Metadata:** Information about files like size, permissions, owner, timestamps.
* **Structure:** Directories, files, inodes, superblocks.

---

### **Inodes**

* Every file/directory has an inode.
* Stores metadata: permissions, ownership, size, timestamps, pointers to data blocks.
* Does **not** store filename (filename stored in directory entry).

---

### **Links**

#### **Hard Links**

* Multiple filenames point to the same inode.
* Cannot cross filesystem boundaries.
* Deleting one link does not delete data until all hard links are gone.

#### **Symbolic (Soft) Links**

* Special file pointing to another file path.
* Can cross filesystem boundaries.
* Deleting the original file breaks the symlink.

#### **Tools**

* `ln` → create links

  * `ln file link` → hard link
  * `ln -s file link` → symbolic link
* `stat` → view inode, links, metadata.

---

### **Disk Usage Tools**

* `df` → shows disk space usage of filesystems. Example: `df -h` for human-readable.
* `du` → shows disk usage of directories/files. Example: `du -sh /home/user`

---

### **Creating Filesystems**

* `mkfs` → make a filesystem on a partition or device.
  Example: `mkfs.ext4 /dev/sdb1`

---

## **4. Mounting & “Ejecting”**

Mounting makes a filesystem accessible in the directory tree.

### **Mounting**

* Mount to `/` → root directory.
* Temporary mount example:

  ```bash
  mount /dev/sdb1 /mnt
  ```
* Permanent mount via **fstab**:
  Edit `/etc/fstab` to define device, mount point, filesystem type, options.

### **Unmounting**

* `umount /mnt` → safely detach a filesystem.

---

## **5. Compression (tar & gzip)**

Used to combine and compress files for storage or transfer.

### **tar**

* Archiving tool (does not compress by default).
* Example:

  ```bash
  tar cvf archive.tar folder/
  ```

  * `c` → create archive
  * `v` → verbose
  * `f` → filename

### **gzip**

* Compression tool.
* Example:

  ```bash
  gzip file.txt
  ```
* Combined example:

  ```bash
  tar czvf archive.tar.gz folder/
  ```

  * `z` → gzip compression

### **Extracting**

```bash
tar xzvf archive.tar.gz
```

* `x` → extract

---

## **6. Quick Reference Commands**

| Task                 | Command                           |
| -------------------- | --------------------------------- |
| List partitions      | `fdisk -l` / `gdisk -l`           |
| Create filesystem    | `mkfs.ext4 /dev/sdX1`             |
| Mount device         | `mount /dev/sdX1 /mnt`            |
| Unmount device       | `umount /mnt`                     |
| Check disk usage     | `df -h` / `du -sh`                |
| Create hard link     | `ln file link`                    |
| Create symbolic link | `ln -s file link`                 |
| View metadata        | `stat file`                       |
| Archive files        | `tar cvf archive.tar folder/`     |
| Compress archive     | `tar czvf archive.tar.gz folder/` |

---

If you want, I can also make a **visual one-page diagram** showing **devices → partitions → filesystems → mounting → links → commands** which will make it extremely fast to memorize for finals.

Do you want me to make that diagram?
