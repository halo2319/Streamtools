# How to use ModDeck

ModDeck puts the chats you moderate on **Twitch, YouTube, Kick and TikTok** into one
feed, with one set of mod tools. This guide walks through everything, in the order you
will need it. (For the technical background and limits, see `README.md`.)

---

## 1. Installing ModDeck

You only do this once per computer. It takes about five minutes.

You will need:

- **Node.js**, version 18 or newer (free).
- **Google Chrome or Microsoft Edge.** ModDeck opens it so you can sign in the normal way. Most people already have one.
- An internet connection, for the first launch and for chat itself.

You do **not** need developer accounts, API keys, tokens or any files to edit.

### Step 1: Install Node.js

1. Go to https://nodejs.org and download the **LTS** version (the big green button).
2. Run the installer and accept the defaults.
3. Check it worked: open a terminal (Windows: search for **Command Prompt**; Mac: open **Terminal**) and type:

   ```
   node --version
   ```

   You should see a number like `v20.11.0`. Any number of 18 or higher is fine. If you see
   "not recognized" or "command not found", restart the computer and try again.

### Step 2: Get the ModDeck folder

1. Put the ModDeck zip file somewhere you will remember (for example your Documents folder).
2. **Unzip it**: on Windows right-click it and choose **Extract All**; on Mac double-click it.
3. Open the new folder (named something like `moddeck Beta 1.0`). You should see
   `server.js`, `README.md`, a `public` folder, and the three start files.

Tips:

- Do **not** run ModDeck from inside the zip file. Unzip it first.
- Keep the folder somewhere you can write to, because ModDeck saves your sign-ins and message history in it.
- The folder can live anywhere, but do not move it while ModDeck is running.

### Step 3: Start it for the first time

Follow section 2 below. On the first start ModDeck sets itself up automatically if it needs to
(you will see "Setting up ModDeck for the first time..." in the terminal window). If the
`node_modules` folder came with your copy, this step is skipped and it starts straight away.

Then sign in to your platforms (section 3) and add your chats (section 4). That is the whole installation.

### Installing it for other moderators

Each moderator installs their own copy on their own computer and signs in with their own account.
Before you send your copy to someone:

- **Delete everything inside the `data` folder** (or send a copy made without it). It holds your
  sign-ins and your saved chat history, which must never be shared.
- You can leave out the `node_modules` folder to make the file much smaller. It is set up again
  automatically on first start (that computer needs an internet connection for this).

### Updating

To update ModDeck, unzip the new version into a **new** folder, then copy your old `data` folder into
it. That keeps your sign-ins, chat list and message history. (Combined streams and hidden streams are
saved in your browser, not in the folder, so they stay as they were.)

### Uninstalling

Close ModDeck and delete the ModDeck folder. That removes everything it saved, including your
sign-ins. Node.js can be uninstalled separately like any other program. You can also sign out of a
platform first from **Manage chats**.

---

## 2. Starting ModDeck

Do this every time you want to moderate (and once to finish installing).

| Computer | Do this |
|---|---|
| Windows | Double-click **Start ModDeck.bat** |
| Mac | Double-click **Start ModDeck.command** (if macOS blocks it, right-click it and choose Open) |
| Linux | Run `./start.sh` in a terminal (if it says permission denied, run `chmod +x start.sh` first) |

A black terminal window opens and your browser opens ModDeck at `http://localhost:3000`.

- **Leave the terminal window open.** ModDeck only works while it is running.
- If ModDeck is already running, starting it again just opens the browser to it.
- To stop ModDeck, close the terminal window (or press `Ctrl+C` in it).

## 3. Signing in

You sign in once per platform, using the account that moderates the chats.

1. Click **Sign in with Twitch / YouTube / Kick**. You will see these on the empty screen,
   or as a coloured **sign in** tag at the top of the page.
2. Your normal Chrome or Edge opens. Log in with your username and password like you always do.
   Complete any extra check Google or Cloudflare asks for.
3. **Close that window yourself.** ModDeck notices and finishes the sign-in. If the
   tag at the top says **click here when signed in**, you can click it instead.

The tags at the top show each platform's state: **live** (working), **connecting**,
**sign in** (needs you to sign in), or **problem** (hover over it for details).

To sign out, open **Manage chats** and click **Sign out** next to that platform.

**TikTok needs no sign-in.**

## 4. Adding the chats you moderate

Click **Manage chats** (top right). Each platform has its own section.

### Twitch
- Chats you moderate are **found automatically** after you sign in.
- Tick or untick a channel to choose whether ModDeck joins it. (If you moderate a lot of
  chats, only the first 30 are joined automatically; tick the rest you want.)
- If the list is empty, type a channel name (or paste its link) and click **Add**.
- Channels you added yourself have a **Remove** button.

### YouTube
- When a stream you moderate goes live, paste its link (for example
  `youtube.com/watch?v=...`) and click **Add**.
- If the stream is not live yet, ModDeck waits for it.

### Kick
- Type the channel name (or paste the link) and click **Add**.

### TikTok
- Type the username and click **Add**. TikTok is **read-only** (see the table in section 12).

Click **Done** when finished. Added chats are remembered for next time.

## 5. A tour of the screen

- **Top bar:** platform status tags, **Manage chats**, and the **search box**.
- **Left column:**
  - **Platforms:** switch a whole platform on or off in the feed.
  - **Streams:** every chat you have added, with its messages per minute. Click one to
    focus on it, or click **All streams** to see everything. **Hide / Show** mutes one stream's chat.
  - **Combine:** joins streams together (see section 9).
- **Middle:** the **video**, with tabs for each platform and a dropdown to pick the channel.
- **Right column:** the **chat**, with three tabs:
  - **Chat:** the live feed, the mod tools, and the send box.
  - **Actions:** a log of what you did.
  - **Watch:** your watch words.

On a narrower window the left column folds away. The same choices then appear as a row of
chips above the chat.

## 6. Reading chat

- Every message shows a small **platform icon**, the time, the user name (with a **mod** tag
  for moderators), and the channel it came from.
- New messages arrive at the bottom. Scroll up to read older ones; a button appears to jump back to the latest.
- **Click a user name** to see only that person's messages. Press `Esc` or click **Show all** to clear it.
- **Search:** type in the search box (or press `/`) to filter by words or names.
- When anything is filtering the chat (a hidden platform or stream, **This stream**, a person,
  or a search), an amber bar tells you and offers **Show all**.
- **Past messages:** ModDeck keeps up to 5000 messages from the last 7 days, so they are
  still there after a restart. Scroll to the top or click **Show earlier messages** to load more.
  When ModDeck joins a chat it also tries to fill in what was said just before.

### Watch words
Open the **Watch** tab and type words separated by commas (for example `discord.gg, free followers`).
Messages containing them are highlighted. This is only for you; nobody else sees it.

## 7. Sending messages

At the bottom of the chat there is a send box.

1. Pick the chat in the dropdown on the left of the box.
2. Type your message and press **Enter** (or click **Send**). Press `c` to jump to the box.

What to know:

- **Your own messages appear in the feed** right away, like everyone else's. On Twitch they
  appear when Twitch confirms the message was posted. If Twitch refuses a message (for example
  in slow mode, followers-only mode, or a duplicate), it simply does not appear in the feed and
  ModDeck does not show an error, so if a Twitch message never shows up, check the chat's rules.
- **Length limits:** YouTube 200 characters, everything else 500.
- **TikTok cannot be sent to** (it has no chat API). Use the TikTok app.
- A chat that is not live yet cannot be sent to; you will see an error.

### Sending to several chats at once
In a combined stream (section 9) the dropdown has an **All in <name>** option, and a
**Send to:** row of platform buttons appears above the box. Switch a platform on or off to
choose exactly where the message goes: one platform, a few, or all. A chat that is not live
is skipped quietly.

## 8. Moderating

**Click a message.** A bar of tools appears under the chat:

| Button | What it does |
|---|---|
| **Delete** (`d`) | Removes that one message |
| **Timeout** (`t`) | Times the person out. Pick the length first: 30 sec, 1 min, 10 min, 1 hour, 1 day, 7 days |
| **Warn** (`w`) | Sends a warning. **Twitch only** |
| **Ban** (`b`) | Bans the person. **Press it twice**: the first press changes it to **Confirm ban** for a few seconds |
| **Unban** | Lifts a ban |
| **Everywhere…** (`e`) | Acts on the person on several platforms at once (below) |

Extras in the same bar:

- **Reason (optional):** goes with the timeout, ban or warning. If you leave it empty, ModDeck uses "Moderated via ModDeck".
- **Also in my other <platform> chats:** tick it and a timeout, ban, warning or unban is applied in
  every chat you moderate on that platform, not just this one. (Not available for Delete.)

When an action works you see a short confirmation. If it fails you see why. Messages from
someone you timed out or banned are greyed out. Messages removed by other moderators
disappear from your feed too (not on TikTok).

Everything you do is listed in the **Actions** tab, and also saved in `data/actions.log`.

### Everywhere (one person, every platform)
Use this when the same person is troublemaking on several platforms.

1. Click one of their messages, then **Everywhere…** (or press `e`).
2. Choose the action (ban, timeout, warn or unban), the timeout length if needed, and a reason.
3. ModDeck lists accounts **with the same name** that it has seen in your chats. **Tick only the ones you are sure
   are the same person.** The same name is not always the same person.
4. To add an account that is on another platform under a different spelling, type it into
   **Add their account on another platform** and pick it from the suggestions. It must have chatted in one of your chats.
5. Click the big button (for example **Ban 3 accounts**). A results list shows what worked and what failed.

Each ticked account is acted on in every chat you moderate on that platform. Warnings are Twitch only.

## 9. Combining streams

If one person streams on several platforms at once, combine them into a single stream.

1. In the **Streams** list click **Combine** (or **+ Combine** at the end of the chip row above the chat).
2. Tick **two or more** streams.
3. Type a name and click **Combine**.

You now have one stream with the icons of its platforms: one merged chat in time order, one
video switcher, and an **All in <name>** send option.

- **Rename:** double-click its name.
- **Split:** click **Split** to separate them again.
- You can combine a combined stream with more streams.
- Combined streams are saved **in your browser**, so they are there next time you use the same browser.

## 10. Video

The stream video is the main view.

- Switch platform with the tabs above the video and pick the channel in the dropdown.
- **Open on site** opens the stream in a new tab.
- Tick **Video follows the chat I click** and clicking a message switches the video to that stream.
- **This stream** (above the chat) shows only the chat of the video you are watching.
- **Hide video** gives the whole width to chat. Click it again (**Show video**) to bring the video back.
- Videos start **muted**.
- **TikTok** does not allow its video to be embedded, so you get an **Open TikTok LIVE** button instead. Its chat still shows.
- If a YouTube stream will not play, its owner may have turned off embedding. Use **Open on site**.

## 11. Keyboard shortcuts

| Key | Does |
|---|---|
| `j` / `k` (or arrow keys) | Move to the next / previous message |
| `d` | Delete the selected message |
| `t` | Timeout |
| `w` | Warn (Twitch) |
| `b` | Ban (press twice) |
| `e` | Everywhere |
| `c` | Go to the send box |
| `/` | Go to search |
| `Esc` | Clear the selection, the person filter, or leave a box |

Shortcuts do not trigger while you are typing in a box.

## 12. What works on each platform

| | Twitch | YouTube | Kick | TikTok |
|---|---|---|---|---|
| Read chat | yes | yes | yes | yes |
| Finds your chats for you | yes | no (paste link) | no (type name) | no (type name) |
| Send a message | yes | yes (200 chars) | yes | no |
| Delete | yes | yes | yes | no |
| Timeout | yes | yes (fixed 5 min) | yes | no |
| Ban / unban | yes | yes (undo only for bans made here this session) | yes | no |
| Warn | yes | no | no | no |

Other YouTube notes: bans can only be fully undone in YouTube Studio, and "everywhere" actions on YouTube
only work for people who have chatted in that chat since ModDeck started.

## 13. If something goes wrong

| Problem | Try this |
|---|---|
| "Run npm install first" | Close ModDeck and start it with the start file again (it installs what it needs), or run `npm install` in the folder |
| ModDeck says it needs Chrome or Edge | Install one of them, then sign in again |
| A platform tag says **sign in** | Click it and log in again. Logins can expire |
| A platform tag says **problem** | Hover over it to read the reason. Signing in again fixes most of them |
| Kick says it was blocked (Cloudflare) | Sign in to Kick again |
| Twitch shows no chats | Open **Manage chats** and add the channel names yourself |
| YouTube shows "waiting to go live" | The stream is not live yet. It starts by itself when it is |
| "Not live yet" when sending | That chat is not connected yet. Wait for its tag to say **live** |
| A Twitch message you sent never appears | Twitch refused it (slow mode, followers-only, a duplicate message, or a ban). ModDeck shows no error for this, so check the chat's rules on Twitch |
| Your combined streams or hidden streams are gone | They are saved in the browser. A different browser, a private window, or cleared browser data starts fresh |
| One platform stopped working after it worked before | Platforms change their websites without warning. That platform may need a ModDeck update |

## 14. Staying safe

- ModDeck only listens on your own computer and refuses connections from other websites.
- Your sign-ins are stored in the **`data/` folder**. **Never share that folder** (or send it in a zip).
- ModDeck uses the platforms' own website calls, which are **unofficial**. This may go against their
  terms, and it is used at your own risk.
- This is a first version and has **not been tested against live accounts**. The Kick and YouTube
  moderation calls and the Twitch fallback are the most likely to need small fixes.
