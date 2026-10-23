# Phase 3: Directory Permissions

## Objective

Create a shared projects directory for the design team and a restricted billing
directory for the finance group.

## Directory plan

| Path | Owner | Group | Mode | Purpose |
|---|---|---|---|---|
| `/srv/studio/projects` | `root` | `design` | `2770` | Shared design work |
| `/srv/studio/billing` | `root` | `finance` | `2770` | Restricted billing files |

## Create the directories

```bash
sudo mkdir -p /srv/studio/projects /srv/studio/billing
```
`mkdir -p` creates the directory paths, including missing parent directories.

## Set ownership

```
sudo chown root:design /srv/studio/projects
sudo chown root:finance /srv/studio/billing
```

`chown` assigns administrative ownership to `root` and assigns each directory

to its corresponding team group.

## Set directory permissions

```
sudo chmod 2770 /srv/studio/projects /srv/studio/billing
```

The leading `2` enables setgid on each directory, so new entries inherit the

directory's group. The `770` permissions grant full access to the owner and

group and no access to other users.

## Set the team file-creation mask

```
echo 'umask 0002' | sudo tee -a /home/claire/.profile
echo 'umask 0002' | sudo tee -a /home/eider/.profile
echo 'umask 0002' | sudo tee -a /home/taylor/.profile
```

The `umask` setting allows group write permission in the usual default file

creation modes. It is applied when each account starts a new login session.

## Configuration check

```
ls -ld /srv/studio /srv/studio/projects /srv/studio/billing
grep -n 'umask 0002' /home/claire/.profile
grep -n 'umask 0002' /home/eider/.profile
grep -n 'umask 0002' /home/taylor/.profile
```

Record the actual output and note any differences from the expected owner,

group, and permission settings.

## Screenshots

Directory owner, group, and mode:

![Directory owner, group, and mode](/docs/screenshots/05-studio-directory-permissions.png)

The `umask` setting in the three user profiles:

![The umask setting in the three user profiles](/docs/screenshots/06-team-umask-settings.png)

## Notes

Access tests for each account will be documented in Phase 4.
