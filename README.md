# Premium Audio Company

## Guidelines for Contributing to Web Project Repositories

We use a workflow based off of "RemoteFlow", which is defined in detail here: https://www.buink.com/a-continuous-deployment-git-branching-model/

Refer to that URL as needed, but the steps and rules we will follow are outlined below.

## Workflow Overview

The basic rules that must be followed are:

1. All new work is to based off the `main` branch. That is the single source of truth and the only branch that is considered to be stable.
2. All work is to be done in separate branches, and when ready to be tested on staging, the branch should be pushed to `origin` and a Pull Request into the `develop` branch must be made.
3. After the PR is approved, it'll be merged into `develop` and thus automatically deployed to a staging site for UAT.
4. After testing is complete and the `feature` is approved for production, the `feature` branch is merged into `main` and deployed to the production server, and it will be deleted from `origin`.

## Steps to follow as a Contributor

If you are working on a feature or bugfix, here are the general steps to follow:

### 1. Create your branch

ALWAYS branch new features/work off the `main` branch. Call your new branch something like `feature/something-meaningful`. (If you are fixing a bug, use something like `bugfix/something-meaningful` instead.) Example:

```
git checkout main; git checkout -b feature/something-meaningful;
```

### 2. Make your changes

Make your changes on your new `feature` branch locally, commiting to it as necessary.

### 3. Keep your branch up-to-date as needed

Merge the `main` branch from `origin` back into your `feature` branch often to make sure it is up-to-date. Example:

```
git checkout feature/something-meaningful; git pull origin main;
```

### 4. Test locally

Be sure to test your feature thoroughly within you local dev environment.

### 5. Push to `origin`

When ready, push your branch to `origin`. Example:

```
git push origin feature/something-meaningful
```

### 6. Submit a PR

Create a Pull Request on GitHub repository, into the `develop` branch. The lead developer will be notified by GitHub automatically.

After the PR is reviewed, it'll either be approved and merged into `develop` by the lead developer, or it'll be commented on for additional changes/info if it's not yet approved.

### 7. Test on Staging

After the PR is approved and the feature is deployed to staging, it's a good idea to do your own final testing of the feature on the staging site, just for one last check. If something looks odd, please make sure you notifiy the lead developer. If it looks fine to you, no further action is required by you for that feature, unless notified otherwise.
