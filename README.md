# Demo LLM Agent Cypress Test Writer in Dagger TypeScript SDK ✍️🤖🧪

## Run in `dagger shell` and let the LLM use Dagger tools to write a new Cypress test!

Start a dev Dagger Engine with LLM support using:
https://github.com/shykes/melvin/blob/main/README.md

Load the module into Dagger Shell:
- `cd cypress-test-writer`
- `dagger shell`

Once in shell, run:
- `llm` to ensure you're hooked up to your LLM
- `cypress-test-update https://github.com/jpadams/hello-dagger-ts`


https://github.com/user-attachments/assets/0432be8b-08bb-4b2f-9409-f0175cc5bbc2


After getting a successful test built try:
- `cypress-test-update https://github.com/jpadams/hello-dagger-ts | terminal`
and check out your new Cypress test in `cypress/e2e/`.

Increase verbosity to 4 and/or view in Dagger Cloud for best results :)

Fun to try:
- in `hello-dagger/` notice you're on the `green` branch, run `git diff main` this is what is used to build the new test
- check out the `prompt.txt` in `cypress-test-update/`
- `hello-dagger/.dagger` is present. The app is Daggerized! In the directory try:
  `dagger shell -c 'build | up'` and other fun things :)

Notes:
- note the `contest:e2e` target in the `package.json`
  - I used `concurrently` to manage running the dev server and Cypress in one command
  - I used `--success first` to ensure the test exit code propagated, not the SIGTERM shutdown of the dev server
- I am not a TypeScript dev, so there are likely much better ways to do this :D
