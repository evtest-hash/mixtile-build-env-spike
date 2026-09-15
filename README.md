# build-env-spike

Throwaway repository. It exists only to establish facts about a GitHub-hosted
`ubuntu-24.04` runner as a **native (non-Docker)** build environment for
cross-built arm64 Debian/Ubuntu rootfs and disk images.

It builds no product and contains no application code. Delete it once the
questions below are answered.

Questions under test:

1. Runner base environment: root, loop devices, mount, mknod, udev, disk, CPU.
2. Are the usual rootfs/packaging/cross-build dependencies installable from the
   `noble` archive, and at what versions?
3. Can `mmdebstrap` from `noble` bootstrap arm64 `bookworm`, `trixie`, `noble`
   and `resolute`?
4. Is a `qemu-aarch64` binfmt handler present, and does it carry the `F`
   (fix-binary) flag?
5. Do `losetup --partscan` / `parted` / `mkfs.ext4 -O ^orphan_file` / `mount` /
   raw `dd` work without a privileged container?
6. How fast is `apt` inside an emulated arm64 chroot?

No Docker is used anywhere in the workflows, by design.
