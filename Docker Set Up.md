---

# Docker Setup on Personal RHEL

This guide documents a repeatable way to install Docker CE on a personal RHEL system and addresses a couple of common issues. It utilizes Red Hat Enterprise Linux (RHEL) as this is a commong platform within enterprises. 

It removes any old docker components/installs since its easy for these to create conflicts. It goes without saying that you shouldn't do this step if you using your current Docker install. This guide presumes the reader has limited Docker experience. 

It intentionally avoids EPEL and Red Hat entitlements to reduce conflicts.

---

## Assumptions

* Personal RHEL instance (not registered with Red Hat Subscription Manager)
* RHEL 8, 9 or 10
* `sudo` access
* Internet connectivity
* Goal: stable Docker environment to aid with security lab set up (e.g., Juice Shop, Kali, security testing)

---

## 1. Clean Out Any Existing Docker Artifacts (Do NOT follow this step if you have a Docker install you are currently using/dependant on)

Remove any previously installed Docker or container runtime packages:

```bash
sudo dnf remove -y docker docker-client docker-client-latest \
  docker-common docker-latest docker-latest-logrotate docker-logrotate \
  docker-engine docker-ce docker-ce-cli containerd.io runc
```

Optional cleanup:

```bash
sudo dnf autoremove -y
```

Verify Docker is gone:

```bash
rpm -qa | grep docker
```

Expected result: **no output**

---

## 2. Disable EPEL (Important)

EPEL can introduce dependency conflicts (e.g., `pass`, `git-core`) that are not required for Docker.

```bash
sudo dnf config-manager --set-disabled epel || true
```

Confirm active repositories:

```bash
dnf repolist
```

Expected: only `rhel-*` and possibly `codeready-builder`

---

