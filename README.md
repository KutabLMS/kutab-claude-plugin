# Kutab

Kutab runs Quran and Arabic academies: students, teachers, lessons, attendance,
subscriptions and payments. This plugin connects Claude to one academy so an
admin can ask questions about it in plain language and get reports and
graphics in the academy's own brand.

## What's inside

| Part | What it does |
|---|---|
| **Kutab connector** (`https://mcp.kutab.co/mcp`) | Read-only access to the academy's data through five tools: `academy_branding`, `describe_model`, `query`, `find`, `read_text`. Nothing is written or deleted. |
| **academy-insights** skill | Tells Claude how to answer questions about the academy with those tools: check the data model first, turn names into ids, run one typed query, and say which definition each number uses. |
| **kutab-brand** skill | Makes every visual Claude produces for the academy (cards, certificates, charts, posters) use the academy's real name, logo and colours, in a flat, light, Cairo-font style. |

## Use it

Turn the plugin on, then connect the Kutab connector from the plugin's
Connectors tab. Claude opens Kutab's sign-in page. Use either:

- **Academy admin:** choose "Sign in through your academy instead", type your
  academy's web address, and sign in there with your admin account.
- **Academy owner:** sign in with your Kutab account and the emailed code, then
  pick the academy.

Your academy then asks you to approve the connection. Claude sees only what
your admin account may see. Assistant access must be turned on for the
academy; if the address is refused, ask your academy owner or Kutab support.

Things to ask:

- "What's my academy called, and how many active subscriptions does it have this month?"
- "Which teachers missed the most lessons in the last 30 days?"
- "Make a welcome card for a new student."

## Data

The connector sends Claude's questions to Kutab at `mcp.kutab.co`, which
passes them to your academy and returns the answer: aggregated figures, lists
of records, and text such as lesson notes when Claude asks for it. Every tool
only reads. Kutab and your academy log each call (time, tool, kind of record,
size, outcome) for usage limits and support, never the question's text or the
answer. You can disconnect at any time from Claude or
from your academy's admin panel.

Two other places the plugin can reach, neither of which receives academy data:

- If the connector isn't connected, the kutab-brand skill reads the academy's
  public branding (name, colours, logo) from the academy's own website, at
  the address the admin gives, path /api/info.
- Branded images made from the skill's SVG template load the Cairo font from
  Google Fonts (fonts.googleapis.com) when they are opened.

## Support

business@kutab.co · https://kutab.co/support · Privacy: https://kutab.co/privacy
