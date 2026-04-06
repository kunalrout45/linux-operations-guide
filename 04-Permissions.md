# 🔐 Linux File Permissions & Ownership

Linux is a **multi-user system**, so permissions control:
- Who can read
- Who can write
- Who can execute

---

# 👥 1. Permission Types

Each file/directory has 3 types of users:

| Type   | Meaning              |
|--------|---------------------|
| User   | Owner of the file   |
| Group  | Group owner         |
| Others | Everyone else       |

---

# 🧾 2. Permission Representation

Example:

-rwxr-xr--

Breakdown:

| Section | Meaning |
|--------|--------|
| -      | File type |
| rwx    | User permissions |
| r-x    | Group permissions |
| r--    | Others permissions |

---

# 📂 3. File Types

| Symbol | Type            |
|--------|-----------------|
| -      | Regular file    |
| d      | Directory       |
| l      | Symbolic link   |

---

# 🔑 4. Permission Meaning

| Permission | File Meaning         | Directory Meaning              |
|------------|---------------------|--------------------------------|
| r          | Read file           | List directory contents        |
| w          | Modify file         | Create/Delete files inside     |
| x          | Execute file        | Enter directory (cd)           |

---

# 🔢 5. Numeric (Octal) Permissions

| Permission | Value |
|------------|------|
| r          | 4    |
| w          | 2    |
| x          | 1    |

Example:

rwx = 4+2+1 = 7  
r-x = 4+0+1 = 5  
r-- = 4+0+0 = 4  

Example:

chmod 755 file.txt

---

# 🛠️ 6. Changing Permissions

## Symbolic Method

chmod u+x file.txt
chmod g-w file.txt
chmod o=r file.txt

## Numeric Method

chmod 644 file.txt
chmod 755 script.sh

---

# 👑 7. Ownership Commands

## Change Owner
chown user file.txt

## Change Group
chgrp group file.txt

## Change Both
chown user:group file.txt

---

# 📁 8. Directory Permissions (VERY IMPORTANT)

Directory permissions behave differently:

| Permission | Meaning |
|------------|--------|
| r          | Can list files (ls) |
| w          | Can create/delete files |
| x          | Can enter directory (cd) |

---

# ⚠️ 9. Directory vs File Permissions (Key Concept)

👉 Directory permissions OVERRIDE file permissions in many cases.

### Example:

- File has: rw-r--r--
- Directory has: --- (no permissions)

➡️ You CANNOT access the file at all.

### Key Rules:

- Without **x on directory** → cannot access files inside
- Without **r on directory** → cannot list files
- Without **w on directory** → cannot create/delete files

---

# 🔥 10. Special Permissions

## 1. SUID (Set User ID)

- Applied on executables
- Runs with owner's privileges

Example:

chmod u+s file

Symbol: s (in user execute)

---

## 2. SGID (Set Group ID)

- On files → runs with group privileges
- On directories → new files inherit group

Example:

chmod g+s dir/

---

## 3. Sticky Bit

- Used on shared directories
- Only owner can delete their files

Example:

chmod +t dir/

Common Example:
 /tmp directory

---

# 🧾 11. Numeric Special Permissions

| Permission | Value |
|------------|------|
| SUID       | 4    |
| SGID       | 2    |
| Sticky     | 1    |

Example:

chmod 4755 file  (SUID)
chmod 2755 dir   (SGID)
chmod 1755 dir   (Sticky)

---

# 🧠 12. ACL (Access Control Lists)

ACL allows **fine-grained permissions beyond user/group/others**

---

## Enable ACL (if needed)

yum install acl

---

## Check ACL

getfacl file.txt

---

## Set ACL

setfacl -m u:kunal:rwx file.txt

---

## Remove ACL

setfacl -x u:kunal file.txt

---

## Default ACL (for directories)

setfacl -m d:u:kunal:rwx dir/

---

# ⚡ 13. umask (Default Permissions)

Controls default permission for new files

Example:

umask 022

Result:
- Files → 644
- Directories → 755

