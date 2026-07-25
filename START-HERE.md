# START HERE

Welcome. This folder is a small kit that puts your website on the internet, for free,
using GitHub Pages. Once it is set up, publishing is **one double-click**: you change
your web pages, double-click `PUBLISH.bat`, wait about a minute, and your live site is
updated.

You do not need to know anything about Git, the command line, or web servers. The only
skill you need is writing HTML files. Everything else is handled for you.

**How to use this guide:** do every part below, in order, one time. The first setup
takes about fifteen minutes. After that you are done for good, and from then on you only
ever double-click `PUBLISH.bat`.

A quick word on the files already in this folder. You can look, but you do not need to
touch any of them to get started:

    START-HERE.md                  <- this guide
    PUBLISH.bat                    <- the button you double-click to publish
    my-github-details.EXAMPLE.txt  <- a template you copy and fill in (Part 6)
    html_files\                    <- put your web pages in here
    unlisted\                      <- optional: pages that exist but are not listed
    README.md                      <- a list of your pages; rebuilt automatically
    .gitignore                     <- keeps your password file off the internet

Do **not** type your details into `README.md`. It is rewritten from scratch every time
you publish, so anything you put there is erased. This guide is `START-HERE.md`, and it
is the only document you need to read.

---

## What you will end up with

A live website at:

    https://YOUR-ACCOUNT-NAME.github.io

For example, if your account name is `jane`, your site is `https://jane.github.io`.
Every HTML page you put in the `html_files` folder gets its own tidy web address with no
".html" on the end: a file called `about.html` is live at `https://jane.github.io/about`.

---

## The seven parts

You will do these once, in this order. None of them is hard.

    Part 1  Install Git for Windows
    Part 2  Make a GitHub account
    Part 3  Make your repository (the home for your site)
    Part 4  Turn on publishing
    Part 5  Make your access token
    Part 6  Fill in your details file
    Part 7  Add your web pages and publish

---

## Part 1 - Install Git for Windows

`PUBLISH.bat` uses a free program called **Git** behind the scenes, so install that
first.

1. Go to https://git-scm.com/download/win
2. The download starts on its own. Run the file you downloaded.
3. An installer opens with a lot of screens. You do not need to understand them: just
   click **Next** on every screen, then **Install**, then **Finish**.
4. Restart your computer once, to be safe.

That is the only program you have to install.

---

## Part 2 - Make a GitHub account

GitHub is the free service that will host your website.

1. Go to https://github.com and click **Sign up**.
2. Pick a username, an e-mail address, and a password, and follow the prompts.
3. **Write down your username and the e-mail address.** You need both in Part 6.

Your username becomes part of your website address, so choose one you like: username
`jane` gives the site `https://jane.github.io`.

---

## Part 3 - Make your repository

A "repository" is just the folder on GitHub that holds your site. It has to have an exact
name.

1. Sign in to GitHub, click the **+** in the top-right corner, then **New repository**.
2. In **Repository name**, type your account name followed by `.github.io` and nothing
   else. If your account name is `jane`, type:

        jane.github.io

3. Set it to **Public**. A free personal site must be public. (See "A note on privacy" at
   the end of this guide.)
4. **IMPORTANT: leave the repository completely empty.** Do **not** tick
   **"Add a README file"**, and do not add a license or a .gitignore either. If any of
   those boxes is ticked, your very first publish will fail with a clash. Leave every box
   unticked.
5. Click **Create repository**.

---

## Part 4 - Turn on publishing

Two quick settings, both on your new repository's **Settings** page.

**4a. Tell GitHub to build your site with Actions**

1. On your repository, click **Settings** (in the top row).
2. In the left menu, click **Pages**.
3. Under **Build and deployment**, find **Source** and choose **GitHub Actions** from the
   dropdown. Do not pick "Deploy from a branch".

That is what turns your pages into a live website automatically.

**4b. Let the publisher update your page list**

1. Still in **Settings**, in the left menu click **Actions**, then **General**.
2. Scroll down to **Workflow permissions**.
3. Choose **Read and write permissions**, then click **Save**.

If you skip 4b your website still works. The only thing that stops is the automatic list
of your pages inside `README.md`, which quietly goes out of date. It is a small thing, but
it takes ten seconds, so do it now.

---

## Part 5 - Make your access token

A "token" is a special password that lets `PUBLISH.bat` publish on your behalf. You make
it once.

1. Go to https://github.com/settings/tokens
2. Click **Generate new token**, then choose **Generate new token (classic)**.
3. **Note:** type anything you like, for example `my website`.
4. **Expiration:** choose **No expiration**, so you never have to redo this.
5. **Tick two boxes:** `repo` and `workflow`. Both are needed. A token without the
   `workflow` box cannot publish a website.
6. Click **Generate token**.
7. GitHub shows the token **only once**. It starts with `ghp_`. Copy it now and keep the
   page open until you have pasted it into your details file in Part 6. If you ever lose
   it, just make a new one.

**Treat this token like a password.** Anyone who has it can change your GitHub account.

---

## Part 6 - Fill in your details file

Now you tell the kit who you are. This is the step people most often trip on, so go
slowly.

**6a. Make your own copy of the template**

1. In this folder, right-click `my-github-details.EXAMPLE.txt` and choose **Copy**, then
   right-click an empty part of the folder and choose **Paste**. You now have a second
   file.
2. Rename the copy to exactly `my-github-details.txt`. That is the template's name with
   `.EXAMPLE` removed.

**Watch out for a Windows trap here.** Windows often hides file endings. When it does, the
template shows up as `my-github-details.EXAMPLE` with no `.txt`, and renaming your copy can
accidentally leave you with `my-github-details.txt.txt`. Two ways to stay safe:

- Simplest: when Windows hides endings, just name the copy `my-github-details` and Windows
  keeps the `.txt` for you.
- Or turn endings back on: in the folder, open the **View** menu and tick
  **File name extensions**, then rename the copy to `my-github-details.txt`.

(Good news: even if you do end up with `my-github-details.txt.txt`, `PUBLISH.bat` accepts
that name too. But the clean name is tidier.)

**6b. Fill in your copy, and never the EXAMPLE file**

Open **your copy** (`my-github-details.txt`) by double-clicking it; it opens in Notepad.
Replace each `PASTE_..._HERE` with your own value:

    GITHUB_USERNAME   your GitHub account name (from Part 2)
    GITHUB_EMAIL      the e-mail on your GitHub account (from Part 2)
    GITHUB_REPO       your repository name: your account name plus .github.io
    GITHUB_TOKEN      the token you made in Part 5 (the one starting ghp_)

Three easy-to-miss rules for each line:

- No spaces in front of the name.
- No spaces around the `=` sign. Good: `GITHUB_USERNAME=jane` Bad: `GITHUB_USERNAME = jane`
- Nothing after your value, and no trailing spaces.

Save the file (Ctrl+S) and close it.

**Fill in YOUR COPY, never `my-github-details.EXAMPLE.txt`.** The EXAMPLE file is uploaded
to GitHub on purpose, so it must never hold a real token. If you type your token into the
EXAMPLE file by mistake, `PUBLISH.bat` will notice and stop you before anything leaks, but
it is easiest to simply always edit your own copy.

**Never share this folder once your token is in it.** Your `my-github-details.txt` stays
private on your PC, because `.gitignore` keeps it from ever being uploaded to GitHub. But
that protection is about uploading only. If you e-mail this folder, put it in a ZIP you
send to someone, or post a screenshot of the file, you are handing over your token. Do not
do that. If a token ever leaks, delete it at https://github.com/settings/tokens and make a
new one.

**A note about your e-mail.** GitHub stamps `GITHUB_EMAIL` onto every change you publish,
and your repository is public, so that address is permanently visible to anyone who looks.
If you would rather not show your real e-mail, GitHub can give you a private forwarding
address that looks like `12345678+jane@users.noreply.github.com`. Open
https://github.com/settings/emails , tick **Keep my email addresses private**, copy the
`...@users.noreply.github.com` address it shows you, and use that as your `GITHUB_EMAIL`.

---

## Part 7 - Add your web pages and publish

**7a. Put your pages in the folder**

Your web pages live in the `html_files` folder. Put your `.html` files there.

- The file named `index.html` is your **home page**, the first thing visitors see at
  `https://YOUR-ACCOUNT-NAME.github.io`. There is a blank one there now for you to replace.
- Every other file gets its own clean web address. A file `html_files\about.html` becomes
  `https://YOUR-ACCOUNT-NAME.github.io/about`. You can use sub-folders too:
  `html_files\guides\setup.html` becomes the address ending in `/guides/setup`.

There is also an `unlisted` folder. It works exactly like `html_files`, except pages in it
are **not shown in any list** (not on your home page and not in `README.md`). Two things to
understand about it:

- **"Unlisted" means "not linked", not "private".** Your repository is public, so an
  unlisted page is still readable by anyone who knows or guesses its address, and it is
  visible in your project's history on github.com. Do **not** put anything secret in
  `unlisted`. It is only for pages you simply do not want in your menus.
- **Never put an `index.html` inside `unlisted`.** It would quietly replace your real home
  page. Your home page's `index.html` belongs in `html_files`.

**7b. Publish**

Double-click **`PUBLISH.bat`**.

A black window opens and shows what it is doing, in plain English. When it finishes it
tells you your website is on its way and shows your address. GitHub then needs **about a
minute** to build the new version, so wait a moment, then open your site in a browser:

    https://YOUR-ACCOUNT-NAME.github.io

That is it. Your website is live.

---

## Every day after this

Setup is done. From now on, publishing changes is just three steps:

1. Edit, add, or delete `.html` files in the `html_files` folder.
2. Double-click `PUBLISH.bat`.
3. Wait about a minute, then refresh your site.

You never touch the token, the settings, or this guide again.

---

## If something goes wrong

If `PUBLISH.bat` cannot publish, it stops and shows a message in plain English, on screen,
that tells you exactly what to do. **Read that on-screen message first**: it is written for
the exact problem you hit, and it never changes anything on GitHub when it stops.

Here are the messages it can show, so you can find yours quickly. The heading on your
screen matches this list word for word:

- **"Git is not installed on this computer."** Do Part 1: install Git for Windows from
  https://git-scm.com/download/win , restart, and try again.
- **"I cannot find your details file."** You have not made your `my-github-details.txt`
  copy yet, or it is not in this folder. Do Part 6.
- **"You filled in the wrong file."** You typed your details into
  `my-github-details.EXAMPLE.txt`. Put the `PASTE_..._HERE` words back into it, then fill in
  a copy named `my-github-details.txt` instead (Part 6).
- **"One of your details is missing."** One of the four lines could not be read, usually
  because of a space in front of the name, a space around the `=`, or nothing after the
  `=`. Fix that line and save.
- **"You have not filled in all your details yet."** A line still has the example
  `PASTE_..._HERE` text in it. Replace it with your own value.
- **"Your repository name has a slash in it."** `GITHUB_REPO` must be the repository name
  only, like `jane.github.io`, not `jane/jane.github.io`.
- **"I could not set this folder up for publishing."** The folder is read-only or sits on a
  network or cloud drive. Move this folder to your Desktop and try again.
- **"I could not read the files in this folder."** A file is still open in another program.
  Close your editor and any open documents, then try again.
- **"I cannot reach GitHub."** Your internet is down or blocked. Check your connection, or
  try another network, and run it again. Nothing was changed.
- **"GitHub would not let me open your repository."** Usually your token is wrong, expired,
  or deleted; or `GITHUB_REPO` or `GITHUB_USERNAME` is spelled differently on GitHub. Check
  each one letter by letter.
- **"I could not save a snapshot of your folder."** Check that `GITHUB_EMAIL` in your
  details file is a real e-mail address, then try again.
- **"Your password file was about to be published."** Your `.gitignore` is missing, or its
  first rule was changed. Open `.gitignore` and make sure these two lines are there, in this
  order:

        my-github-details*
        !my-github-details.EXAMPLE.txt

- **"GitHub has a version of a file that clashes with yours."** The same file was changed
  both here and on github.com. The on-screen message names the file and tells you how to fix
  it. **If it is your very first publish, the cause is almost always a repository that was
  not empty:** make a new, completely empty one (Part 3, and do not tick "Add a README
  file"), then try again.
- **"GitHub would not accept your token."** Your token was refused, most often because it is
  missing the `workflow` box. Make a new token (Part 5), tick both `repo` and `workflow`,
  put it in your details file, and try again.
- **"GitHub changed while this was running."** Something updated your repository at the same
  moment. Nothing was lost: just double-click `PUBLISH.bat` again.
- **"GitHub refused the upload."** Something else went wrong while uploading; the window
  shows exactly what GitHub said. If it is not clear, wait a minute and try again.

---

## A note on privacy

A free `<username>.github.io` website must be **public**. That means:

- Anyone can visit your site.
- Anyone can read the files that make up your site on github.com, including any pages in
  `unlisted`.
- Your `GITHUB_EMAIL` is visible in your published history.

Your `my-github-details.txt`, with your token inside it, is the one thing that stays
private, and only because `.gitignore` keeps it off GitHub. Never share this folder, and
you are safe.

---

You are done. Welcome to your website.
