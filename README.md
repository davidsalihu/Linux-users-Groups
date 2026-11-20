Day 7 of #30DaysOfChallenge: Linux Users & Groups 🔐
Imagine a server with 3 developers, 1 admin, and an app running in the background.
Should they all have the same access? Of course not. That's exactly why Linux has users and groups.
👤 Users
Every user has a unique ID (UID). There are 3 types:
• Root (UID 0): full control
• Regular users: for real people
• System users: for apps and services
Check who you are:
whoami → your username
id → your UID, GID and groups
👥 Groups
Instead of setting permissions for each developer, put them in one group and give the group access:
sudo groupadd developers
sudo usermod -aG developers alice
sudo chown :developers /srv/project
sudo chmod 2770 /srv/project
New developer joins? Add them to the group. Done. ✅
💡 Pro tip: always use -a with -G. Without it, you wipe the user's other groups.
🛡️ The big lesson: Least Privilege
Give every user and service only the access they need, nothing more.
Why? If an account gets compromised, the damage stays small.
🔹 Developers → access to the project folder only
🔹 Admin → sudo, not a root login
🔹 Apps → their own system user, never root
If you work with Linux servers, cloud or CI/CD, this isn't optional. It's how you control who can touch what.
What's one permission mistake you've seen (or made)? 👇
#Linux #DevOps #DevSecOps #CloudSecurity #LeastPrivilege #30DaysOfChallenge #TSAcademy #Day07
