<!--
SPDX-FileCopyrightText: 2023 Kalle Fagerberg

SPDX-License-Identifier: CC-BY-4.0
-->

# kubectl-klock's changelog

This project tries to follow [SemVer 2.0.0](https://semver.org/).

<!--
	When composing new changes to this list, try to follow convention.
	The WIP release shall be updated just before adding the Git tag.
	Replace (WIP) by (YYYY-MM-DD), e.g. (2021-02-09) for 9th of Febuary, 2021
	A good source on conventions can be found here:
	https://changelog.md/
-->

## v0.3.1 (2023-08-05)

- Fixed namespace column when using `--all-namespaces` not rendering or
  sorting properly (fd3b165)

## v0.3.0 (2023-08-05)

- Added support for `exec` auth plugin. (5f122fa, #13)

- Fixed spinner still showing when there's no results. (edec13c, #18)

- Fixed not redrawing on update, but instead only on age timer tick.
  Now it redraws immediately. (f65ef48, #20)

- Fixed namespace column not showing when using `--all-namespaces`.
  (8b5a172, #21)

- Fixed non-namespaced resources' `CREATED AT` column not showing as duration.
  (d1323de)

## v0.2.0 (2023-04-28)

- Now available on krew index!

  ```bash
  kubectl krew install klock
  kubectl klock pods
  ```

- Added warning color on pod restarts when >0. (7f7a1b9)

- Added flag `--watch-kubeconfig` / `-W` to restart the watch when your
  kubeconfig (e.g `~/.kube/config`) file was changed. Such as when changing
  context via `kubectl config use-context NAME` or
  [kubectx](https://github.com/ahmetb/kubectx). (25a1f97)

- Added keybinding `f` to toggle fullscreen manually. (30639c5)

- Fixed bug where kubectl-klock would panic after ~50min of inactivity. (#12)

- Added better help text in README and `--help`. (9aa6d22)

- Added support for ARM architecture. All supported architectures: (246223c)

  - darwin/386
  - darwin/amd64
  - darwin/arm64 _(new!)_
  - linux/386
  - linux/amd64
  - linux/arm64 _(new!)_
  - windows/386
  - windows/amd64
  - windows/arm64 _(new!)_

## v0.1.1 (2023-04-17)

- Added `--output wide` / `-o wide` support. (18beed4)

## v0.1.0 (2023-04-16)

- Initial release. Features:

  - Watch arbitrary resources, just like `kubectl get <resource> [name]`

  - Auto updating age

  - Colors on statuses (e.g `Running`) and fractions (e.g `1/1`) to make them
    stand out more

- Supported architectures:

  - darwin/386
  - darwin/amd64
  - linux/386
  - linux/amd64
  - windows/386
  - windows/amd64