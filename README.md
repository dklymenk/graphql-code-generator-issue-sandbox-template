# `graphql-code-generator` `extractAllFieldsToTypes` with `@defer` "Duplicate identifier" reproduction

Reproduction for https://github.com/dotansimha/graphql-code-generator/issues/10867

Run `npm run generate` and look at `types.ts` to find the duplicate `UserQuery_user_User` identifiers.

What works:

- setting `extractAllFieldsToTypes` to `false`
- removing the `@defer`

What doesn't work:

- using the inline fragment `... @defer { email }`
- using the named fragment `...UserEmail @defer`
