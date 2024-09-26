# Terminology

An overview of terms used in the context of EESSI, in alphabetical order.

---

## CernVM-FS { #cvmfs }

*(see [What is CernVM-FS?](https://multixscale.github.io/cvmfs-tutorial-hpc-best-practices/cvmfs/what-is-cvmfs/))*

---

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
