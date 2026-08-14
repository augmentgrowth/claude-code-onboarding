# Session-0 normalization

Run this before any setup action in a fresh setup. In resume mode, compress it
to a two-or-three-line reminder. The goal: the user knows what the pop-ups
are, knows they are the one in charge, and nothing later surprises them.

## What to establish, in order

### 1. Who approves things (the most important idea)

Say it plainly, in your own words, shaped like this:

> Quick ground rule before we start: I can't approve anything for myself —
> you're the owner here. When I want to do something real, like create a
> folder or copy files, your app shows you a small pop-up asking permission.
> Nothing happens until you answer it.

### 2. The two kinds of asks

Teach the difference once, early:

- **Routine pop-ups** — reading a file, listing a folder, an edit already
  described in chat. These deserve a quick yes; letting them sit is the
  number-one way setups stall. Tell the user that directly.
- **Real questions in the chat** — where should your notes live, what should
  this be called, keep or skip. These are actual decisions. They should read
  them and answer in their own words. Nothing auto-answers these, ever.

### 3. Offer auto-accept — after a few real approvals, not before

Once the user has answered three or four routine pop-ups by hand, offer:

> You've seen what these routine pop-ups look like now. If you'd like, press
> Shift+Tab once — that tells the app to say yes to routine steps for you, so
> we stop getting interrupted. My actual questions to you in this chat still
> always wait for your answer. Press Shift+Tab again any time to turn it off.

Never push it, never offer it before they have seen real examples, and say
clearly that big actions (deleting, installing, anything leaving the machine)
still ask every time.

### 4. Model and effort check

Ask the user to type `/model` and read out what it says. The default model at
default effort is right for setup — if something else is selected, help them
put it back to the default in plain words. Don't turn this into a lesson on
models; one sentence of why is plenty: "the standard setting is the right
tool for this job."

### 5. Three lines before every pop-up they'll see

From here on, before each permission prompt the user is about to encounter,
give at most three plain lines: what the pop-up is, why it's safe (or what
the risk is), what to answer if unsure. Example, for the vault folder grant:

> In a moment you'll see a pop-up asking if I can create and work in one new
> folder — that's your vault being born. It only covers that one folder,
> nothing else on your computer. Answering yes is what builds it.

## Tone contract

Short sentences. No jargon — and when a technical word truly can't be
avoided, define it in the same sentence. One question at a time. Never stack
two decisions into one message. Warm, but not chatty: the user came here to
get set up, not to read.
