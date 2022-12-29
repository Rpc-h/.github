# Release Process

The purpose of this process is to streamline the releases of HOPR packages.

- [Release Process](#release-process)
  - [Types of release](#types-of-release)
    - [Internal release](#internal-release)
    - [Public release](#public-release)
  - [When to release](#when-to-release)
    - [Milestone based releases](#milestone-based-releases)
    - [Deadline based releases](#deadline-based-releases)
  - [Testing phases](#testing-phases)
    - [RPCh team testing](#rpch-team-testing)
    - [HOPR team testing](#hopr-team-testing)
    - [Ambassador testing](#ambassador-testing)
  - [Release promotion](#release-promotion)
  - [Creating a new release](#creating-a-new-release)

## Types of release

| Type     | Goal                                                  | Ambassadors | Public |
| -------- | ----------------------------------------------------- | ----------- | ------ |
| Internal | Test new features and bug fixes                       | MAYBE       | NO     |
| Public   | New RPCh release, showcase new features and bug fixes | YES         | YES    |

### Internal release

- Internal releases are more frequent and their goal is to test new features and bug fixes.
- There should be no public involvement unless the [internal release](#internal-release) is promoted to a [public release](#public-release).
- All releases start as an [internal release](#internal-release) and may be promoted to a [public release](#public-release), see [release promotion](#release-promotion).
- When an internal release is created, one of the [representatives](./development.md#representatives) is assigned to oversee the release cycle, this includes:
  - notifies the HOPR team that the [internal release](#internal-release) has been created in element channel `releases`
  - [creating release](#release-cycle)
  - [testing release](#testing-phases)
  - [promoting release](#release-promotion)

### Public release

- Public releases are less frequent and their goal is to showcase new features and bug fixes.
- A [public release](#public-release) occurs when an [internal release](#internal-release) is promoted to a [public release](#public-release), see [release promotion](#release-promotion).

## When to release

### Milestone based releases

At the end of a sprint, if a sufficient amount of features / bug fixes were implemented since last release, the [Representatives](./development.md#representatives) and `founders` may queue and prioritize a new release for the **upcoming** sprint, this happens during [epic prioritization](./development.md#epic-prioritization).
This new release is considered an [internal release](#internal-release) and may be [promoted](#release-promotion) to a [public release](#public-release) if [testing phases](#testing-phases) are successful.

### Deadline based releases

Deadline based releases are releases which have a defined deadline and scope agreed between the [Representatives](./development.md#representatives) and `founders`.
These releases should be of a large scope and occur only on occasions where a release is necessary.

## Testing phases

Testing phases occur only when a release is queued and prioritized during [epic prioritization](./development.md#epic-prioritization).

For every phase completed, release owner must update the release's PR with the current testing phase status.

| Phase name         | Description                                                  |
| ------------------ | ------------------------------------------------------------ |
| RPCh team testing  | First phase, testing by RPCh team members only               |
| HOPR team testing  | Second phase, testing by available HOPR team members         |
| ambassador testing | Third (optional) phase, testing with the help of ambassadors |

### RPCh team testing

- Capture low-hanging bugs which are easily detectable.
- Test new features and bug fixes included in the release.
- Avoid taking resources from the HOPR team members.

### HOPR team testing

- Occurs after [RPCh team testing](#rpch-team-testing) is successful.
- With the help of a [changelog](#release-cycle), test RPCh.

### Ambassador testing

A third and final phase of testing is to include ambassadors.
This is optional in the possibility we want to gather more data points and/or a specific feature requires larger network topology.

- May occur after [HOPR team testing](#hopr-team-testing) is successful.

## Release promotion

- All releases start by being internal releases.
- An [internal release](#internal-release) may be promoted to a [public release](#public-release) when all [testing phases](#testing-phases) are successful.
- Before promoting, release owner ensures that comm team actually needs this to be public.

An [internal release](#internal-release) is promoted to a [public release](#public-release) by tagging its binaries with the public facing release name. See [Deployment checklist](#deployment-checklist).

Once promoted, a release owner notifies the HOPR team that the [internal release](#internal-release) has been promoted to a [public release](#public-release):

- by commenting into the release's epic
- by writing in element channel `releases`

## Creating a new release

1. Create a new branch based from `main` with a name like `release/v<new_version>`, ex: `release/v0.1.1`
2. Before pushing the branch, run `npx changeset` and `npx changeset version`, this will prepare the branch to publish the new release
3. Push branch, workflow will now publish release (only npm packages atm)
4. Create a new [github release](https://github.com/Rpc-h/RPCh/releases/new) use [release v0.1.1](https://github.com/Rpc-h/RPCh/releases/tag/v0.1.0) as reference
