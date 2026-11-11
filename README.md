# UI Designer: a sample to try

A seeded repository for trying **UI Designer**: you design the UI of a sample product with a coding agent and
the `ui-walkthrough` skill, then review it, screen by screen, in the walkthrough viewer.

The product is **Pot Tracker**, a fictional UK pension and investment tracker ([PRODUCT.md](PRODUCT.md)). Everything
the design needs, short of the design itself, is already here:

| Where | What |
| :--- | :--- |
| [`docs/analysis/use-cases/`](docs/analysis/use-cases) | Nine use cases, from signing in to comparing how pots have grown |
| [`docs/analysis/user-personas/`](docs/analysis/user-personas) | The three savers they are for |
| [`docs/analysis/domain/`](docs/analysis/domain) | How pensions are found, projected and compared |
| [`docs/analysis/ui/`](docs/analysis/ui) | The UI's principles, and its look: `tokens.css`, shown in `look-and-feel.html` |
| [`docs/glossary.md`](docs/glossary.md) | The words the product uses |
| [`docs/ui-walkthrough.yaml`](docs/ui-walkthrough.yaml) | The skill's configuration: where views and walkthroughs go, the viewports, where to publish |

What isn't here is the UI: the views and the walkthroughs. That is what you make.

The providers, the people and the figures are made up.

## Getting started

Trying the sample is by invitation. When you are invited you are sent:

* **the skill**, a zip of the `ui-walkthrough` skill, and the **organisation and project** your walkthroughs publish to;
* separately, a **one-time code** to sign in to the viewer, and a **push token** to publish with.

You need a coding agent that runs skills, Git, Node.js 22.18 or later (the skill runs TypeScript directly), and Chrome or
another modern browser.

The skill is plain Node and is meant to work equally well in any coding agent, but so far it is tested only in
[Claude Code](https://claude.com/claude-code), so the steps below use it. With another agent, put the skill in that
agent's skills directory instead of `~/.claude/skills/`, use that path wherever these steps run the skill, and start that
agent where they start `claude`.

### 1. Fork and clone

Fork this repository on GitHub, then clone your fork:

```
git clone https://github.com/<you>/ui-designer-demo.git
cd ui-designer-demo
```

### 2. Install the skill

Unzip the skill into your agent's skills directory, here Claude Code's, then install what it needs to draw: it renders
each screen in a headless Chromium.

```
mkdir -p ~/.claude/skills/ui-walkthrough
unzip ui-walkthrough-*.zip -d ~/.claude/skills/ui-walkthrough
cd ~/.claude/skills/ui-walkthrough && npm install && npx playwright install chromium
```

If Playwright says it does not support Chromium on your system, as it can on a very new Linux release, see
[Playwright's system requirements](https://playwright.dev/docs/intro#system-requirements). Only `render` needs the
browser: `check` and `publish` run on Node alone.

The skill is not public. Keep the zip out of your fork: a fork of a public repository is public.

### 3. Sign in to the viewer

Go to <https://viewer.weaverengineering.co.uk> and sign in with your email address and the one-time code. The code
works once, within 24 hours of being made; you then choose a password of at least 12 characters for every sign-in after.

The demo sleeps when no one is using it. If it is asleep, the first visit wakes it, which takes about a minute.

### 4. Set up publishing

Save the push token in a file named `.ui-walkthrough-push-token` in the directory **above** your clone, outside the
repository, where the skill finds it by default:

```
cd ..                                   # the directory holding ui-designer-demo
cat > .ui-walkthrough-push-token        # paste the token, press Enter, then Ctrl-D
chmod 600 .ui-walkthrough-push-token
```

Or set it in the environment instead, as `UI_WALKTHROUGH_PUSH_TOKEN`. Never commit it.

Then, in `docs/ui-walkthrough.yaml`, replace the placeholder project with the one you were given:

```yaml
publish:
  project: your-organisation/your-project      # the organisation and project you were sent
  service: https://viewer.weaverengineering.co.uk
```

### 5. Design

Work on a branch. Each branch is a stream of revisions in the viewer, compared with `main`.

```
git checkout -b design/sign-in
claude
```

Ask the agent to design a use case with the skill, for instance:

> Use the ui-walkthrough skill to design the UI for the sign-in use case,
> `docs/analysis/use-cases/sign-in/USE-CASE.md`, following `docs/analysis/ui/PRINCIPLES.md` and the tokens in
> `docs/analysis/ui/tokens.css`. Draw it on desk and phone. Render it, check it, commit it and publish it.

The agent writes the views (`docs/analysis/ui/views/`) and a walkthrough (`docs/analysis/ui/walkthroughs/sign-in/`), then
runs the skill from `docs/`:

| Command | Does |
| :--- | :--- |
| `node ~/.claude/skills/ui-walkthrough/ui-walkthrough.ts render --walkthrough analysis/ui/walkthroughs/sign-in` | draws every step, and writes its pages |
| `node ~/.claude/skills/ui-walkthrough/ui-walkthrough.ts check` | lists every problem, and what is still pending |
| `node ~/.claude/skills/ui-walkthrough/ui-walkthrough.ts publish` | pushes the project to the viewer, as a new revision on your branch's stream |

Commit before you publish, so the revision is the commit you reviewed.

A good order is the one the use cases lean on: **sign-in** first, since every other screen sits inside what it draws,
then **find-my-pensions**, with **claim-a-possible-match** nested in its step 5a.

For a worked example, the branch
[`run-through/WVR-280`](https://github.com/weaver-engineering/ui-designer-demo/tree/run-through/WVR-280) holds those
three walkthroughs, designed this way and reviewed in the viewer. Look at it after you have tried your own, or when you
are stuck: the point is to see how the skill and the review shape a design, not to copy one.

### 6. Review

Open your project in the viewer. Each walkthrough is a flow you page through, step by step, in each viewport, down into
a nested walkthrough and back up; each view has a page of its own.

Comment on any screen. Then press **Review**, then **Copy**, and paste the review into your agent's session: it reads
every comment, with the step and screen each is about, and changes the design. Render, check, commit and publish again,
and the viewer says your stream has moved to the new revision, with **Follow it** to open it.

If you'd rather the viewer in a window of its own than a tab, there is a Chrome extension; ask for its zip, unzip it, and
in `chrome://extensions` turn on **Developer mode**, choose **Load unpacked** and pick the unzipped directory.

### Publishing from CI

The sample has no CI, and you need none: publishing from your machine is enough. If you want your fork to publish on
every merge to `main`, a job on a GitHub-hosted runner can run `publish` from `docs/`, with the push token in the
repository secret `UI_WALKTHROUGH_PUSH_TOKEN`. The demo's certificate is a public one, so nothing else needs trusting.
The job has to install the skill first, and the skill is not public, so fetch it from somewhere private to you, never
from your fork.

## Requesting an invitation

Invitations come from whoever told you about UI Designer: ask them, and they will set you up.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).
