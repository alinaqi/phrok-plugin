---
name: phone-calls
description: Place and follow up real outbound phone calls with the Phrok tools (make_call, schedule_call, get_call, list_calls, hangup_call, get_account). Use when the user asks you to call someone, book or change a reservation or appointment, check opening hours or stock by phone, or asks how a call went.
---

# Phone calls with Phrok

An AI voice agent makes the call, introduces itself as an AI assistant calling on the user's behalf,
pursues the goal you give it, and reports back a transcript, summary and outcome.

## Tools

- `make_call(to, goal, context?, language?, max_minutes?)` — call now.
  - `to`: E.164 with country code (e.g. `+14155550123`). Convert local formats; ask if the country is unclear.
  - `goal`: one or two sentences of what the call must achieve.
  - `context`: every fact the agent may use (names, dates, booking references, acceptable alternatives). The agent never invents anything else.
  - `language`: `en` (default), `de`, `ar`, … (non-English needs the Pro plan).
- `schedule_call(..., scheduled_for)` — the same at a future ISO-8601 time.
- `get_call(call_id)` — status, transcript, summary, outcome.
- `list_calls()`, `hangup_call(call_id)`, `get_account()` (plan, minutes and credits left, caller ID).

## How to run a call

1. Show the user the number, goal, context and language, and wait for an explicit "yes" before `make_call` or `schedule_call`. Never call without confirmation.
2. After `make_call`, wait about 20 seconds, then poll `get_call` every 15–20 seconds until the status is `completed`, `busy`, `no_answer`, `voicemail`, `failed` or `canceled`.
3. Report in 2–4 lines: the outcome, key facts (times, prices, confirmation numbers) and anything the user must do. Offer the transcript.
4. Busy or no answer: say so and offer to retry later with `schedule_call`.

## Rules

- Only call numbers the user asked you to call. Never emergency or premium-rate numbers, or anyone who asked not to be called.
- Never ask the agent to pretend to be human, make payments, sign up for anything, or share personal data beyond the context.
- If a call is refused (for example "verify your email", "out of minutes"), tell the user why and share the link in the error message. Don't retry automatically.
