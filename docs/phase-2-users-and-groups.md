# Phase 2: Users and Groups

## Objective

Create local user accounts and role-based groups for the creative studio scenario.

## Account and group plan

| Account | Role | Supplementary group | Administrative access |
|---|---|---|---|
| `claire` | Designer | `design` | No |
| `eider` | Designer | `design` | No |
| `taylor` | Finance administrator | `finance` | No |
| `labadmin` | Lab administrator | `sudo` | Yes |

## Create the groups

```bash
sudo addgroup design
sudo addgroup finance
```
These groups represent the studio's design and finance teams. Group-based

permissions will be configured in Phase 3.

## Create the accounts

```
sudo adduser claire
sudo adduser eider
sudo adduser taylor
```

`adduser` creates each local account and its home directory. Passwords are

entered interactively and are not documented in this repository.

## Assign supplementary groups

```
sudo usermod -aG design claire
sudo usermod -aG design eider
sudo usermod -aG finance taylor
```

The `-aG` options add a supplementary group while preserving any existing

supplementary group memberships.

## Verification

Document the results of:

```
id claire
id eider
id taylor
getent group design
getent group finance
getent group sudo
```

Expected membership:

- `claire` and `eider` belong to `design`.
- `taylor` belongs to `finance`.
- The three scenario accounts are not members of `sudo`.

## Screenshots

Users and groups created

![Users and groups created](/docs/screenshots/04-users-groups-created.png)

