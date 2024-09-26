# Terminology

An overview of terms used in the context of EESSI, in alphabetical order.

---

## CernVM-FS { #cvmfs }

*(see [What is CernVM-FS?](https://multixscale.github.io/cvmfs-tutorial-hpc-best-practices/cvmfs/what-is-cvmfs/))*

---

## Client { #client }

A **client** in the context of CernVM-FS is a computer system on which a CernVM-FS [repository](#repository)
is being accessed, on which it will be presented as a [POSIX](https://en.wikipedia.org/wiki/POSIX)
read-only file system in a subdirectory of `/cvmfs`.

---

## Proxy { #proxy }

A **proxy**, also referred to as *squid proxy*, is a forward caching
[proxy server](https://en.wikipedia.org/wiki/Proxy_server) which acts as an intermediary between a CernVM-FS
[client](#client) and the [Stratum-1 replica servers](#stratum1).

It is used to improve the latency observed when accessing the contents of a [repository](#repository),
and to reduce the load on the [Stratum-1 replica servers](#stratum1).

A commonly used proxy is [Squid](http://www.squid-cache.org).

For more information on proxies, see the
[CernVM-FS documentation](https://cvmfs.readthedocs.io/en/stable/cpt-squid.html).

---

## Repository { #repository }

A CernVM-FS **repository** is where the files and directories that you want to distribute via CernVM-FS are
stored, which usually correspond to a collection of software installations.

It is a form of [*content-addressable storage (CAS)*](https://en.wikipedia.org/wiki/Content-addressable_storage),
and is the single source of (new) data for the file system being presented as a subdirectory of `/cvmfs`
on [client](#client) systems that [mount](https://en.wikipedia.org/wiki/Mount_(computing)) the repository.

!!! note

    A CernVM-FS repository includes [**software installations**](#software-installations),
    not [*software packages*](https://en.wikipedia.org/wiki/Package_format) like RPMs.

## Software *installations* { #software-installations }

An important distinction for a CernVM-FS repository compared to the more traditional notion of a
[*software repository*](https://en.wikipedia.org/wiki/Software_repository) is that a CernVM-FS repository
provides access to the **individual files** that collectively form a particular software installation, as opposed to
housing a set of [*software packages*](https://en.wikipedia.org/wiki/Package_format) like RPMs,
each of which being a *collection of files* for a particular software installation that are *packed together*
in a single *package* to distribute as a whole.

!!! note

    This is an important distinction, since CernVM-FS enables only downloading the specific files that are
    required to perform a particular task with a software installation, which often is a small subset of all
    files that are part of that software installation.

---
