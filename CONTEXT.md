# CONTEXT

The shared vocabulary for FeyFey. Terms here mean exactly what this file says they
mean, on this site and in the product. If a word is being used loosely, it belongs
here with a definition instead.

## Product

**FeyFey** — The product. A video spaced repetition tool for turning passive video
watching into active recall.

**Recall** — The earlier working name for the same product. Still visible in the
preview build's interface and in some internal storage keys. It is not a separate
product and not a feature; it is a name awaiting a rename.

## Study model

**Item** — One video in a learner's library, together with everything attached to
it: its title, subject, priority, pre-watch question, bookmarks and scheduling
state. The unit the scheduler operates on. An item is not the video file; an item
*refers to* a file.

**Video file** — The media itself. Held only on the learner's own device. Distinct
from an item, and deliberately so: an item can exist on a device where its video
file does not.

**Title** — The learner's name for an item. It *defaults* to the video file's name
when the item is created, but it is a separate thing and editing it changes nothing
on disk. "Renaming a video" always means renaming its title.

**File name** — The name the video file had when it was added. Recorded against the
item and never edited, because it is the only way a learner can recognise which file
to pick when re-attaching the item on another device. Distinct from the title, which
drifts away from it as soon as the learner renames anything.

**Bookmark** — A label a learner writes, paired with a timestamp in a video.
Bookmarks point *into* a video. They are not general notes and are not free-standing.
Each bookmark has an identity of its own that survives being renamed or moved to a
different timestamp, so a bookmark is the same bookmark after an edit, not a
replacement for the one that was there.

**Pre-watch question** — A question the learner writes to be shown *before* the
video plays, so an answer is attempted before the video supplies one. The mechanism
that makes a session active rather than passive.

**Subject** — A learner-defined grouping label for items, such as a course or topic.
Free text, not a fixed taxonomy.

**Priority** — High, medium or low. Affects only the order in which *new* items enter
the queue. It does not influence scheduling once an item has been reviewed.

**Teach-back** — A video a learner records of themselves explaining something. It is
a *usage pattern*, not a distinct kind of item: the product stores and schedules a
teach-back exactly like any other video. Do not describe it as a feature.

## Scheduling

**Review** — One pass over an item: answering the pre-watch question, watching, and
rating. Reviews are what the schedule counts.

**Rating** — The learner's judgement at the end of a review: Forgot, Hard, Good or
Easy. The only input the scheduler takes.

**Interval** — The number of whole days until an item's next review. Produced by a
rating.

**Ease factor** — A per-item multiplier that grows when an item is rated Easy and
shrinks when it is rated Hard or Forgot. Governs how fast that item's intervals widen.

**Due** — An item whose next review date is today.

**Overdue** — An item whose next review date has already passed. Distinct from due,
and ordered ahead of it.

**New** — An item that has been added but never reviewed.

**Queue** — The ordered, truncated list of items presented for one day's session:
overdue first, then due, then new, cut off at the daily goal.

**Daily goal** — The learner-chosen maximum number of items in a day's queue. A cap
on the session, not a target to hit.

## Boundaries

**Local-first** — The property that video files are stored only on the learner's own
device and are never transmitted. The product's central design decision, and the
source of its main trade-offs.

**Library metadata** — Everything about items *except* the video files: titles,
subjects, priorities, questions, bookmark labels and timestamps, and scheduling state.
This is what synchronises between devices.

**Preview** — The currently deployed build. Early, incomplete, and labelled as such
wherever it is linked.

**Local dev mode** — A way of running the product with no account at all, available
only when it is served from a developer's own machine. Nothing is transmitted and
nothing syncs. It exists so the interface can be worked on without a real learner's
credentials; it is not a free tier, not a trial, and not something a learner can
reach.
