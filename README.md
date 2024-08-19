## Description

This sample application demonstrates how to use a GitHub Action to run Playwright tests against a simple Node.js Express.js application that logs in with FusionAuth.

It's part of the article available at: https://fusionauth.io/docs/get-started/run-in-the-cloud/github-actions.

## Run the app

To run this application you will need Node.js and Docker installed. In a terminal run the code below.

```bash
git clone https://github.com/FusionAuth/fusionauth-example-github-actions.git
docker compose up
```

In another terminal run the code below.

```bash
cd app
npm install
npm run start
```

Browse to the app at http://localhost:3000 and log in with `admin@example.com` and `password`.

In another terminal test the app.

```shell
cd app
npx playwright install-deps
npx playwright install
npx playwright test --project=chromium;
# npx playwright test --project=chromium --ui; # to watch the test and see where it fails
```

## Run the tests in a GitHub action

> By default, GitHub prevents action workflows from running on forked repositories. To grant permission for the workflow to execute, navigate to the Actions tab on your forked repository in GitHub and click on the **I understand my workflows, go ahead and enable them** button on the repository.

To run these tests in a GitHub action, fork this repository, change the branch name in `.github/workflows/test.yaml` from `main_RENAME_THIS_TO_ENABLE_TEST` to `main`. Commit and push. The action will start running in the Actions tab in the repository site.


