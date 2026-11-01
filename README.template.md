<!--
  README STANDARD for Kiro Crew app repositories.

  How to use this file:
  1. Copy it to README.md and replace every {{PLACEHOLDER}}.
  2. Keep every "##" heading below, in this order, with this wording: the
     check in capture/check_readme.py (run by CI) looks for them.
  3. Write the user-facing sections (everything above "Development") for someone
     who has never used a terminal: short sentences, the words they will see on
     screen in **bold**, no internal names, no jargon. If a word needs a
     glossary, use a different word.
  4. Describe only what the app does TODAY. Read the app's code before claiming a
     feature. A limit is a fact the reader needs, so say it plainly. A use case
     or a step must be something a reader can do today through the app's own
     screens; a feature only the API can fill goes in a clearly marked note.
  5. Capture the pictures with capture/ (see capture/README.md), never by hand,
     and give every image alt text that says what is IN the picture.
  6. Delete these comments, then walk through CHECKLIST.md.
-->

# {{APP_DISPLAY_NAME}}

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="docs/media/hero-dark.png">
  <img src="docs/media/hero-light.png" alt="{{HERO_ALT_TEXT: what the main screen shows, in one sentence}}">
</picture>

**{{TAGLINE: one line, under 15 words, says what it does for the reader}}**

{{APP_DISPLAY_NAME}} is an app for [Kiro Crew](https://github.com/kirodotdev/KiroCrew),
the open-source personal AI agent.

## What it is

<!-- Two to four sentences. What appears in Kiro Crew once it is on (a page in
     the sidebar? an agent? a scheduled job?), and what it does. -->

{{WHAT_IT_IS}}

**Get started:** {{GET_STARTED: one line with the exact clicks that turn the app
on, e.g. "Open **Apps → Discover**, find **My App**, choose **Install**, then
**Enable**." Link to [Install](#install) for the details.}}

## The problem it solves

<!-- The situation the reader is in before they have this app, in their words.
     Then one sentence on how the app changes it. Mention what it deliberately
     does NOT do if that is part of the point. -->

{{THE_PROBLEM}}

## Top 3 use cases

<!-- Three real situations, most common first. Each: a one-paragraph scenario
     ("You are ... and want ...; you ...") and one screenshot of that moment. -->

### 1. {{USE_CASE_1_TITLE}}

{{USE_CASE_1_SCENARIO}}

![{{USE_CASE_1_ALT_TEXT}}](docs/media/use-case-1-light.png)

### 2. {{USE_CASE_2_TITLE}}

{{USE_CASE_2_SCENARIO}}

![{{USE_CASE_2_ALT_TEXT}}](docs/media/use-case-2-light.png)

### 3. {{USE_CASE_3_TITLE}}

{{USE_CASE_3_SCENARIO}}

![{{USE_CASE_3_ALT_TEXT}}](docs/media/use-case-3-light.png)

## Watch it

![{{WALKTHROUGH_ALT_TEXT: what the recording walks through}}](docs/media/walkthrough.gif)

[Watch the walkthrough as a video (MP4)](docs/media/walkthrough.mp4).

<sub>Recorded from a real Kiro Crew ({{KIROCREW_COMMIT}}) on a throwaway home with
made-up demo data. {{HOW_IT_WAS_MADE: e.g. "No AI model was connected: the
agent's replies were written for this demo and played back by Kiro Crew's offline
test backend, so a real agent's wording will differ. Waits for replies are
shortened."}}</sub>

## Install

**From the Kiro Crew App Store**

1. In Kiro Crew, open **Apps → Discover** in the left sidebar.
2. Search for **{{APP_DISPLAY_NAME}}** and choose **Install**.
3. {{ONLY IF THE APP RUNS ITS OWN CODE: Kiro Crew asks **Trust “{{APP_DISPLAY_NAME}}”
   to run its own code?** Say in one sentence why the app needs its own code,
   then say plainly that trusting it gives that code the same access Kiro Crew
   has (your files, your saved sign-ins and the internet), as the dialog says.
   Then: choose **Trust this app**. You can take it back later in **Settings →
   Security → Third-party apps**.}}
4. The app installs switched off. Choose **Enable** on its page. It then shows
   up under **Apps** in the sidebar and in **Apps → Library**.

{{REQUIREMENTS in plain words: which computers, and what must already work (e.g.
"Kiro Crew must already be able to chat: if ordinary chats work, this works").
Accounts or keys needed, or "none".}}

## First run

<!-- What the reader sees the very first time (an empty list? a setup step?),
     and the one thing to do first. -->

{{FIRST_RUN}}

## How to use it

<!-- The everyday loop as numbered steps, using the exact button and tab names. -->

1. {{STEP_1}}
2. {{STEP_2}}
3. {{STEP_3}}

## Settings & data

- **Where your data lives:** {{DATA_LOCATION, e.g. `~/.kiro/crew/apps/{{APP_NAME}}/data/` (or under `$KIROCREW_HOME` if you set it)}}
- **What leaves your computer:** {{NETWORK_USE: what is fetched or sent, and to whom; "nothing" if nothing}}
- **Turn it off:** **Apps → Library**, open the **⋯** menu on {{APP_DISPLAY_NAME}}, choose
  **Disable**. Your data is kept.
- **Remove it:** the same menu, **Uninstall**. **Keep app data** is ticked by
  default; untick it to delete the data too.

## Troubleshooting / FAQ

<!-- The questions a new user actually asks, each answered in two or three
     sentences. Include every on-screen error message the app can show. Say what
     the reader SEES and what to DO ("the plug icon at the top right is green
     when Kiro Crew is running"), never an internal term ("the gateway is
     connected", "owner_only", "a model it can use"). -->

**{{QUESTION_1}}**
{{ANSWER_1}}

## Development

<!-- For contributors: layout, tests, terminal install, and how to refresh the
     pictures. -->

### Install from a clone

```bash
git clone {{REPO_URL}}
kirocrew app install ./{{REPO_DIR}}
kirocrew app enable {{APP_NAME}}
```

{{ONLY IF THE APP RUNS ITS OWN CODE: `kirocrew app enable` is refused with
`app_execution_denied` until the app is trusted, and there is no command-line
trust step. Enable it from **Apps → Library** instead: that opens the trust
dialog, and **Trust this app and enable** does both.}}
`kirocrew app disable {{APP_NAME}}` turns it off;
`kirocrew app uninstall {{APP_NAME}}` keeps the data and adding `--purge-data`
deletes it.

### Tests

```bash
python -m pip install -r tests/requirements.txt
python -m pytest
```

### Re-capture the README media

The pictures and the recording come from a real, isolated Kiro Crew gateway
driven by [`capture/`](capture/README.md). After any change to what the app shows:

```bash
python capture/capture.py --kirocrew /path/to/KiroCrew
python capture/check_readme.py
```

Then look at every image and at a few frames of the video before committing
(see [CHECKLIST.md](CHECKLIST.md)).

## License

Apache License 2.0. See [LICENSE](LICENSE) and [NOTICE](NOTICE).
