# Warm Mode Examples

Warm mode is for plain text that people read and act on: patient information, help text, notifications and messages. It keeps the clarity rules of strict mode and adds a calm, human voice. See the Warm Mode section of `SKILL.md` for the rules.

These examples are original illustrations built for this skill. They are not quotes from any real product, leaflet or system. Each warm version keeps every fact and hedge of its "before" text and adds none.

Check a warm text in two steps:

1. Run `scripts/ste-lint.py --mode warm`. Fix every hard finding. Read each advisory finding and decide.
2. Read the text for the habits that the linter cannot check: "you", a reassurance the source supports, a reason, everyday words and proportion.

## Example 1 — Side effects: a reassurance the source supports

**Before:**
> Gastrointestinal adverse events, including nausea and diarrhea, are commonly reported and generally resolve within a few days of initiating treatment.

**Strict:**
> Nausea and diarrhea are common side effects. They usually stop within a few days after the start of treatment.

**Warm:**
> You may feel sick or have diarrhea when you start the medicine. This is common and usually settles within a few days.

What changed:
- The reader is "you", and "feel sick" replaces "nausea".
- The reassurance ("usually settles within a few days") comes from the source. "Generally" became "usually", so the hedge keeps its strength.
- No reason was added, because the source gives none.

## Example 2 — A real, serious risk stays plain

**Before:**
> WARNING: This medicine can cause dangerous, potentially fatal allergic reactions. Stop taking it immediately and seek emergency medical attention if you experience swelling of the face, lips or throat, or difficulty breathing. These reactions are rare.

**Warm:**
> Serious allergic reactions are rare, but they can be life-threatening. If your face, lips or throat swell, or you find it hard to breathe:
>
> 1. Stop taking the medicine.
> 2. Get emergency help at once.

Kept as-is: "life-threatening", because the source states a risk of death.

What changed:
- Proportion: the source's "rare" now comes first, before the risk.
- Two stacked fear words ("dangerous, potentially fatal") became one plain statement of the same risk.
- The two actions became a numbered list, one instruction for each step.
- The urgency did not change: "at once" keeps "immediately".

`--mode warm` reports "life-threatening" as an advisory fear word. The writer keeps it on purpose and says so in the `Kept as-is:` line.

## Example 3 — A loose fear word: name the harm

**Before:**
> Patients suffering from asthma should inform their physician before commencing treatment. Concomitant use of alcohol is dangerous, as alcohol potentiates drowsiness.

**Warm:**
> If you have asthma, tell your doctor before you start this medicine. Avoid alcohol while you take it, because alcohol makes you more sleepy.

What changed:
- "Suffering from" became "have".
- The source names the harm: drowsiness. So the warm text says that harm instead of "dangerous".
- The source's reason became a short "because".

If the source named a serious harm, such as slowed breathing, the warm text would say that harm plainly.

## Example 4 — Help text

**Before:**
> Authentication failure. Your session has expired due to inactivity. Unsaved changes may have been lost. Re-authentication is required to proceed.

**Strict:**
> Your session ended because there was no activity. Changes that you did not save may have been lost. Sign in again.

**Warm:**
> We signed you out because the page was idle for a while. Any changes that you did not save may have been lost. Sign in again to continue.

What changed:
- "We" and "you" name the actors. The reason does not blame the reader.
- The hedge stays: "may have been lost".
- The last sentence says why the reader should act.

## Example 5 — A message

**Before:**
> Reminder: appointment scheduled for 10:00 tomorrow. Non-attendance or cancellation with less than 24 hours' notice will incur a cancellation charge.

**Warm:**
> This is a reminder of your appointment tomorrow at 10:00. If you cannot come, please tell us at least 24 hours before. If you tell us later, or do not come, we charge a cancellation fee.

What changed:
- Nouns that hide actions ("non-attendance", "cancellation", "notice") became verbs with a person who acts.
- The text says what to do before it states the fee. The fee stays plain.

## Example 6 — The everyday word first

**Before:**
> Monitor for signs of hypoglycemia, including diaphoresis, tremor and tachycardia, and administer fast-acting glucose if these occur.

**Warm:**
> Check for signs of low blood sugar (hypoglycemia), such as sweating, shaking and a fast heartbeat. If you have these signs, take some fast-acting sugar (glucose).

What changed:
- Each medical word became the everyday word. The exact term follows in brackets where the reader will meet it again, for example on a label or from a doctor.
- "Such as" keeps the meaning of "including": the list gives examples, not every sign.
- One instruction per sentence.

## Example 7 — Present perfect is fine

**Before:**
> Should payment already have been remitted, please disregard this notice.

**Warm:**
> If you have already paid, please ignore this message.

What changed:
- Plain verbs replace formal ones ("paid", "ignore").
- Present perfect stays, because it says that the payment is complete now. Strict mode reports it as advisory. Warm mode does not report it.
