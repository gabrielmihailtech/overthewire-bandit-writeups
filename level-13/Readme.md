Bandit Level 13 → Level 14

---
Summary

The objective of this level was to obtain access to the bandit14 account using a provided SSH private key instead of a password.
The key was stored in the home directory and required proper SSH authentication.

---
Analysis

The home directory contained the file:

**sshkey.private


The contents of the file were inspected to confirm that it was a valid OpenSSH private key:

**cat sshkey.private


The SSH key was then used in an attempt to authenticate as bandit14.

**ssh -i sshkey.private bandit14@localhost -p 2220


A connection attempt was established, but authentication from localhost was blocked by the OverTheWire environment.

Additional troubleshooting steps included:

**ls -l sshkey.private


to verify permissions and:

**chmod 600 sshkey.private


to restrict access to the private key.

---
Commands Used
**ls

**cat sshkey.private

**ssh -i sshkey.private bandit14@localhost -p 2220

**ls -l sshkey.private

**chmod 600 sshkey.private

---
Findings
A valid OpenSSH private key was provided.
The key belongs to the bandit14 account.
Direct access to /etc/bandit_pass/bandit14 as bandit13 resulted in:
Permission denied

SSH authentication must be performed using the supplied private key.
Localhost SSH connections are restricted within the OverTheWire environment.

---
Key Concepts Learned
SSH private key authentication
File permission management
SSH connection troubleshooting
Difference between password authentication and key-based authentication

---
Conclusion

This level introduced SSH key authentication. Rather than using a password, access to the next account is obtained through a private SSH key.
Proper key permissions and understanding SSH authentication methods are essential skills when working with Linux systems and security environments.

---
Skills:
SSH | Linux Permissions | Authentication | Troubleshooting


