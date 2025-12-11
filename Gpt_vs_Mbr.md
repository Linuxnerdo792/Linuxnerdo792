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

Sure! Let’s break it into two parts. First, I’ll give you a **detailed comparison of GPT vs MBR** with lots of points, then I’ll create **25 snippet-style questions with answers** for your final prep.

---

## **GPT vs MBR – Detailed Differences**

| Feature                      | MBR (Master Boot Record)                                                 | GPT (GUID Partition Table)                                       |
| ---------------------------- | ------------------------------------------------------------------------ | ---------------------------------------------------------------- |
| **Introduction**             | Old standard (1983)                                                      | Modern standard (1990s, popular with UEFI)                       |
| **Partition Limit**          | 4 primary partitions (or 3 primary + 1 extended with logical partitions) | Up to 128 partitions by default (Linux/Windows)                  |
| **Disk Size Support**        | Max 2 TB                                                                 | Supports disks larger than 2 TB (up to 9.4 ZB theoretically)     |
| **Boot Method**              | Works with BIOS                                                          | Works with UEFI (modern firmware)                                |
| **Partition Table Location** | First sector of the disk                                                 | First sector + backup at end of disk                             |
| **Redundancy**               | No redundancy                                                            | GPT keeps multiple copies of the partition table for reliability |
| **Error Checking**           | Basic                                                                    | CRC32 checksum to detect corruption                              |
| **File System Independence** | Any filesystem can be used                                               | Any filesystem can be used                                       |
| **Recovery**                 | Difficult, single point of failure                                       | Easier due to backup tables and checksums                        |
| **Compatibility**            | Supported by almost all OS, older hardware                               | Requires modern OS and UEFI; some older OSes don’t boot from GPT |
| **Bootloader Storage**       | Bootloader stored in MBR sector                                          | Bootloader usually stored in EFI system partition (ESP)          |
| **Usage Today**              | Mostly legacy or small drives                                            | Standard for modern PCs, SSDs, NVMe                              |

**Key Notes:**

* GPT is future-proof, MBR is mostly legacy.
* GPT allows better reliability and more partitions.
* MBR can still be useful for old BIOS systems or very small disks.

---

## **25 Snippet-Style Questions with Answers**

Here are conceptual and practical snippet questions based on **Filesystems & Disks**:

---

### **Devices & Partitions**

1. **Q:** Check all partitions on a disk `/dev/sda`.
   **A:** `fdisk -l /dev/sda`

2. **Q:** Show GPT partitions on `/dev/nvme0n1`.
   **A:** `gdisk -l /dev/nvme0n1`

3. **Q:** Create a new primary partition on `/dev/sdb` using `fdisk`.
   **A:** `fdisk /dev/sdb` → `n` → `p` → partition number → default size → `w`

4. **Q:** Convert a disk `/dev/sdc` from MBR to GPT using `parted`.
   **A:** `parted /dev/sdc mklabel gpt`

5. **Q:** Show whether a disk is GPT or MBR.
   **A:** `parted /dev/sda print` or `gdisk -l /dev/sda`

---

### **Filesystems**

6. **Q:** Create an ext4 filesystem on `/dev/sdb1`.
   **A:** `mkfs.ext4 /dev/sdb1`

7. **Q:** Check free space on mounted partitions.
   **A:** `df -h`

8. **Q:** Show disk usage of `/home/user`.
   **A:** `du -sh /home/user`

9. **Q:** Check inode information of `file.txt`.
   **A:** `stat file.txt`

10. **Q:** Create a hard link `linkfile` to `file.txt`.
    **A:** `ln file.txt linkfile`

11. **Q:** Create a symbolic link `symlink` to `file.txt`.
    **A:** `ln -s file.txt symlink`

12. **Q:** Show all filesystem types available.
    **A:** `cat /proc/filesystems`

13. **Q:** Mount `/dev/sdb1` to `/mnt`.
    **A:** `mount /dev/sdb1 /mnt`

14. **Q:** Unmount `/mnt`.
    **A:** `umount /mnt`

15. **Q:** Make `/dev/sdb1` auto-mount at boot in `/etc/fstab`.
    **A:** Add line:

    ```
    /dev/sdb1   /mnt   ext4   defaults   0 0
    ```

---

### **Compression**

16. **Q:** Create a tar archive `archive.tar` of `folder/`.
    **A:** `tar cvf archive.tar folder/`

17. **Q:** Create a gzip-compressed tar archive.
    **A:** `tar czvf archive.tar.gz folder/`

18. **Q:** Extract `archive.tar.gz` to current directory.
    **A:** `tar xzvf archive.tar.gz`

19. **Q:** Just compress `file.txt` using gzip.
    **A:** `gzip file.txt`

20. **Q:** Decompress `file.txt.gz`.
    **A:** `gunzip file.txt.gz`

---

### **Misc / Devices**

21. **Q:** View contents of `/dev/null`.
    **A:** `cat /dev/null` → outputs nothing

22. **Q:** Read 100 bytes of zeros from `/dev/zero`.
    **A:** `head -c 100 /dev/zero`

23. **Q:** Generate 16 bytes of random data.
    **A:** `head -c 16 /dev/random`

24. **Q:** Determine the filesystem type of `/dev/sda1`.
    **A:** `blkid /dev/sda1`

25. **Q:** Create a new GPT disk `/dev/sdd` and a 500MB partition using `parted`.
    **A:**

    ```bash
    parted /dev/sdd
    mklabel gpt
    mkpart primary ext4 0% 500MB
    quit
    ```

---

If you want, I can also **make another 25+ advanced snippet questions focusing on inodes, links, fstab, mounting options, and tar/gzip variations**. Those will be a bit trickier, perfect for a **final exam drill**.

Do you want me to make that next?

