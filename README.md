# Phrok plugin

Give your assistant a phone. Phrok places real outbound phone calls for you — book a table, confirm or
move an appointment, check opening hours — and reports back with the outcome, a short summary and the full
transcript. Calls use a natural full-duplex AI voice, and the agent always says it is an AI calling on your behalf.

## Install

Install **Phrok** from the Grok Bot / Cursor plugin marketplace, then click **Authenticate**. You will be
asked to log in or create a free account at [gb-voice-web.onrender.com](https://gb-voice-web.onrender.com) and
approve access. No API keys to copy.

The plugin contains:

- `mcp.json` — the hosted MCP server `https://gb-voice-api.onrender.com/mcp` (Streamable HTTP, OAuth 2.1 with
  dynamic client registration and PKCE).
- `skills/phone-calls` — instructions that teach the assistant to confirm before calling, poll for results and
  report briefly.

## Try it

- "Call +1 408 609 3679 and ask what time they close." (our public test line)
- "Book a table for 2 tonight at 8 at +1 415 555 0123 under Ali."
- "Schedule a call tomorrow at 10am to confirm my dentist appointment."
- "How did my last call go?" · "How many minutes do I have left?"

## Plans

Free trial (10 minutes, calls to your own verified number), Starter $29/month (120 minutes), Pro $99/month
(500 minutes, all languages), plus prepaid credit packs that never expire. See the
[pricing](https://gb-voice-web.onrender.com/#pricing).

## Safety

Mandatory AI disclosure at the start of every call, do-not-call handling, premium-rate and emergency number
blocking, rate limits, and email verification before the first call. See the
[Acceptable Use Policy](https://gb-voice-web.onrender.com/legal/aup).

## Legal and support

Operated by WorkHub Platform Inc., 1875 S. Bascom Ave, Suite 2400, Campbell, CA 95008, USA.
[Terms](https://gb-voice-web.onrender.com/legal/terms) ·
[Privacy](https://gb-voice-web.onrender.com/legal/privacy) ·
[Imprint](https://gb-voice-web.onrender.com/legal/imprint) · Support: info@workhub.ai
