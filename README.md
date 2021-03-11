# Automatic self reference

[The docs](https://yarnpkg.com/features/protocols#why-is-the-link-protocol-recommended-over-aliases-for-path-mapping)
state that a self reference will be generated for any repository. It is then expected that `packages/config/node_modules/@livingspec`
contains a `configs` directory, but it does not.

# Manual self references (use case we're trying to solve)

`packages/backend` contains two example typescript projects - application and domain. We would like to be able to reference
domain files as `@livingspec/backend/domain` as to keep the possibility of further splits in packages, among other things.
Since a self reference was not created automatically, `packages/backed` has a link to self: `"@livingspec/backend": "link:."`.
This however does not work, there is no `node_modules/@livingspec/backend` folder in `packages/backend`.
