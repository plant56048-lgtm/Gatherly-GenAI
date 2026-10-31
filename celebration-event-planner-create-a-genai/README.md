# Gatherly — GenAI Celebration & Event Planner

Gatherly is a single-file, GenAI-powered planning assistant for weddings, birthdays, anniversaries, and community events. It turns a short event brief into a realistic budget, dated timeline, vendor checklist, and personalized ideas.

## Highlights

- **AI-assisted planning:** Uses Gemini structured JSON output for reliable plans and conversational refinements.
- **Practical budget engine:** Calculates exact INR amounts locally, preserves a contingency reserve, and recalculates cost per guest.
- **Natural-language refinements:** Supports requests such as `30% cheaper`, `cut by 20 percent`, `set guests to 120`, and `add 15 guests`.
- **Vendor diligence:** Tracks vendor status, questions to ask, red flags, and notes. Vendor names retain the casing entered by users, including names such as `DJ` and `MC`.
- **Real timelines:** Scales milestones to the event date without scheduling tasks in the past. Short-lead weddings warn when venues and photographers may already be booked and recommend considering a weekday.
- **Offline-ready starter planning:** Works without an API key through a deterministic local planning engine.
- **Useful exports:** Print a plan, copy a clean summary, export calendar milestones as `.ics`, or download plan data as JSON.

## Run locally

No build step or package installation is required.

1. Download or clone this repository.
2. Open `index.html` in a modern browser.
3. Fill in the event details and select **Generate Plan**.

## Gemini setup

Gatherly defaults to `gemini-3.5-flash`. Open **API Settings**, paste a Gemini API key, and use **Test Connection** before generating an AI plan.

If a model returns HTTP 404 or is no longer available, Gatherly names that model and asks the user to change it in **API Settings**. It does not silently replace that failed AI request with an offline plan.

> For production applications, do not store API keys in browser storage. Route Gemini calls through an authenticated server-side service.

## Suggested refinement prompts

- `Make it 30% cheaper`
- `Cut by 20 percent`
- `Set guests to 120`
- `Add 15 guests`
- `Add a vendor: DJ`
- `Move date to 2026-12-15`
- `Make the menu strictly Jain`

## Tech

HTML, CSS, and vanilla JavaScript. Gemini is called through the Google Generative Language REST API with structured JSON output; all budget math and offline planning logic run in the browser.

## Limitations

- Offline refinements cover common planning requests; broader open-ended changes require a Gemini API key.
- Vendor recommendations are planning categories and diligence prompts, not bookings or verified local-provider listings.
- Calendar export creates all-day milestones; add specific reminder times in your calendar application after import.

## License

Add a license appropriate for your repository before public distribution.
