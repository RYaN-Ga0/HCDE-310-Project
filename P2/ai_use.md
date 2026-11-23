# AI Use Log

This document records how we used AI tools during the development of Snow Compare.

We followed the Stage 4 guidelines by making our own initial project decisions before using AI. We independently defined the problem, target audience, data model, success criteria, and core user flow. We also developed our own initial design sketches before using AI for optional feedback and refinement.

We used AI as a supporting tool for tasks such as reading API documentation, reviewing our existing work, identifying potential gaps, and improving clarity. We remained responsible for the project's requirements, design decisions, technical choices, and final implementation plans.

Each member documents their own AI use, including specifications, prompts, generated output, review, verification, and reflection.

---

## Member A — Product & UX (Murphy Jiang)

### 1. AI Use Overview

**AI tools used:** Claude

**Purpose of AI use:**

I was responsible for the product and UX aspects of Snow Compare. I developed the initial product ideas and design materials before using AI for feedback and refinement.

My AI-assisted tasks included:
- Reviewing the user flow that I developed for the project.
- Checking whether the persona and user journey covered the relevant user needs and interactions.
- Getting feedback on my original mockup sketches and identifying potential usability issues.
- Improving the clarity of UX-related proposal descriptions.
- Checking for missing details or inconsistencies between the user flow, mockups, and proposed features.

I made the initial design decisions and created the original sketches myself. AI was used to review and refine my work, not to replace the initial design process.

### 2. Specification Before Prompting

#### Task 1: User Flow Review

**Task / Feature:** Review my independently developed user flow for comparing ski resort conditions.

**Expected behavior:**
- Inputs: My initial user flow and the project's requirements.
- Expected outputs: Feedback on unclear steps, missing interactions, or potential usability issues.
- Constraints: Preserve the original project concept and MVP scope.

**Checks:**
1. Check that users can understand how to select resorts and begin a comparison.
2. Check that the flow includes comparing forecast data and observed snowpack data.
3. Check that the proposed interactions are consistent with the original project requirements.

#### Task 2: Persona and User Journey Review

**Task / Feature:** Review my independently developed persona and user journey.

**Expected behavior:**
- Inputs: My initial persona, user journey, and identified user needs.
- Expected outputs: Suggestions for missing details or inconsistencies.
- Constraints: Keep the content grounded in our own research and intended target audience.

**Checks:**
1. Check that the persona reflects the intended target audience.
2. Check that the user journey describes a realistic process of comparing ski resorts.
3. Check that the pain points connect to the features proposed in the project.

#### Task 3: Mockup Feedback

**Task / Feature:** Review my original mockup sketches and identify possible usability improvements.

**Expected behavior:**
- Inputs: My original sketches and the planned user interactions.
- Expected outputs: Feedback on layout clarity, information hierarchy, and missing interface elements.
- Constraints: My original sketches and design decisions remain the foundation of the mockups.

**Checks:**
1. Check that the mockups represent the intended user flow.
2. Check that the important comparison information is easy to identify.
3. Check that suggested changes remain within the MVP scope.

### 3. AI Prompts and Generated Output

**Prompts and full transcripts:**

I am working on a UW HCDE 310 group project called Snow Compare. Our project helps users compare ski resort conditions in Washington State.
Our MVP focuses on two resorts: Crystal Mountain and Stevens Pass.
The core user flow we developed ourselves includes three main actions:

Select ski resorts.
Compare weather forecasts and observed snowpack conditions.
Save a comparison.

We independently defined this flow before using AI.
Please review this user flow and identify:

Any missing steps or interactions that users might need.
Any confusing transitions between the three actions.
Potential usability problems for first-time users.
Any features that may be unnecessary for our MVP.

Do not redesign the entire flow or invent additional features. Focus on identifying potential gaps and explaining why they matter.
Please organize your feedback into:

Potential issues
Suggested improvements
Questions we should consider as designers

I'm working only from your three-step description, so some of these gaps may already be covered in your wireframes. Overall, the structure is clear and linear, which is a strength for first-time users. The issues below are mostly about what happens between and inside the steps.

1. Potential issues

Missing steps or interactions

No time frame for the comparison. Forecasts look ahead and observed snowpack looks back. If users can't tell or choose which day or range they're comparing, the data may be accurate but irrelevant to when they plan to ski.
No way back to a saved comparison. The flow ends at "save," but saving only has value if users can return to it. Without that, they may wonder where it went.
Unclear requirements for saving. If saving needs an account, a name, or a confirmation, that creates an unplanned interruption between actions 2 and 3.
No states for missing or outdated data. Weather and snowpack data usually come from outside sources and can lag or fail. Users may trust stale numbers without realizing it.

Confusing transitions

1 → 2: With only two resorts, "select" is either trivial or ambiguous. What happens if someone selects only one? Does the comparison start automatically or after a button press? Can they change resorts from the compare view?
Within 2: Forecast and observed data have different time orientations, and putting them in one step could blur them together.
2 → 3: It's unclear what gets saved: a snapshot of today's numbers or the pairing of resorts. Conditions change, so a snapshot gets stale quickly. It's also unclear where users land after saving.

Usability problems for first-time users

Jargon. Terms like "snowpack" and "base depth" may mean little to casual or beginner skiers, so they may not know which numbers matter.
Comparability. Crystal and Stevens differ in elevation, and measurements may come from different stations or locations. Without context, users may draw wrong conclusions from numbers that aren't truly equivalent.
No sense of "better." Side-by-side numbers show differences but may not help users decide, especially if they don't know what good conditions look like.
Scope expectations. Users may expect other Washington resorts and not understand why only two are offered.

Possibly unnecessary for the MVP

The selection step. With two resorts, it may add a click without adding a real choice.
Saving. This is likely the most expensive action to build, since it brings storage, identity, and retrieval. Make sure the user need justifies it.
Too many metrics in step 2. Anything that doesn't support the user's decision adds clutter for first-timers.
2.

These clarify your existing flow rather than add to it.

Name the one decision the comparison supports (for example, "where should I ski this weekend?") and let it determine what appears in step 2.
State the time frame on screen, and visually separate forecast from observed data.
Show the source and last-updated time for each data type.
Simplify selection. Pre-fill both resorts or clearly explain the two-resort scope up front.
Decide what "save" means (snapshot or live pairing) and label it, so users know what they'll see when they return.
Decide early whether accounts are needed, and define what happens immediately after saving and how users get back to it.
Use plain-language labels with short definitions for technical terms.
Map the edge cases in your flow diagram: one resort selected, data unavailable, and no saved comparisons yet.
Test with someone unfamiliar with skiing, since that will quickly reveal the vocabulary and "so what?" problems.
3.
Who is your primary user: experienced skiers checking quickly, or newer skiers who need more guidance? Are they planning ahead or deciding same-day?
What decision should a user be able to make after viewing the comparison?
Why do users save a comparison: to revisit later, to share, or to track changes over time? Your answer determines what "save" must do.
Do users need to be logged in, and how much friction is acceptable?
How will you handle differences in elevation and measurement location between the resorts?
Which metrics did you choose from user research, and which from assumptions?
What should users do or see right after saving?
How will you know the flow works? For example, what would a successful first-time task look like in a usability test?

Our main users are recreational skiers in Washington. They might be planning a ski trip ahead of time or checking conditions on the day they go. We want to make it easy to quickly compare resorts, rather than focusing too much on beginner guidance.
We want users to decide which resort has better conditions for their ski trip by looking at snowfall, temperature, wind, snow depth, and SWE.
Mainly to come back and look at the comparison later. Sharing and tracking changes over time are not part of our MVP.
No login for now. We want to keep the experience simple. We are considering using local storage to save comparisons in the browser.
We'll show the location and elevation of each SNOTEL station. Since the station might not be at the exact resort location or elevation, we'll make that clear and treat the measurements as nearby reference data.
We chose snowfall, temperature, wind speed, snow depth, and SWE because they are relevant to ski conditions and available through our APIs. These choices are based on our understanding of what skiers care about, and we still need user feedback to validate them.
After saving, users should see a confirmation and be able to find the comparison again.
We'll test with three users. A successful task would be selecting two resorts, understanding their conditions, saving the comparison, and finding it again without much help.

Your answers settle several earlier gaps: no accounts, station context, the purpose of saving, and what success looks like in testing. Reading them together raises some sharper issues.

Newly visible issues

Saving is the biggest tension. With only two resorts, there is only one possible comparison. If "save" stores the pairing and shows live data, every saved comparison is identical and it works like a bookmark. It only becomes meaningfully different if it stores a snapshot (conditions on a specific day) or a chosen date. But you've said tracking over time is out of scope, and your goal is for users to "come back and look later." Decide which one you mean:

Snapshot: label it with the date and time so it isn't mistaken for current conditions.
Live pairing: ask whether saving is worth building at all, since users could just reopen the page.

This also affects how users tell multiple saved comparisons apart, and what "find it again" looks like.

Local storage has a quiet failure mode. Saved items disappear if users clear browsing data, use private mode, or switch devices. That matters for your plan-ahead versus day-of users, who may plan on a laptop and check on a phone. You don't need to change the approach, but a short expectation note at the save confirmation would prevent "where did it go?" moments. Also make sure your usability test uses the same browser throughout.

Check where each metric comes from. SNOTEL stations typically report snow depth, SWE, precipitation, and temperature. Wind isn't a standard SNOTEL measurement, and snowfall is often derived or comes from a forecast. If some metrics come from a forecast point and others from the SNOTEL station, one resort card mixes data from different places and elevations, and your elevation disclosure only covers part of it. Temperature may also appear as both observed and forecast, so label which. Snowfall needs a stated window (past 24 hours? next 24?), or users may confuse it with snow depth.

"Better" has no clear direction. The five metrics don't all point the same way. More snow depth and SWE generally helps, wind can mean closed lifts, and temperature trades snow quality against comfort. Recreational skiers may weigh these well on their own, but this is exactly what testing should check. I'm not suggesting you add a score, just that you notice that the task asks users to synthesize five metrics.

Time frame is still open. You said users might plan ahead or check same day, but the flow doesn't specify which day's forecast they're comparing. Even a fixed MVP choice should be stated on screen.

One adjustment to my earlier jargon point. You don't need beginner guidance, but SWE is the one term many recreational skiers may not recognize. A short label is enough, not a tutorial.

Station disclosure. Good decision, but first-time users often skip footnotes. Check whether people notice it, and whether it carries over to the saved view.

Your test plan

Three users works for finding usability problems, not for measuring anything. A few ways to sharpen it:

"Understanding their conditions" can't be observed directly. Ask "which resort would you pick for Saturday, and why?" and listen for whether they distinguish forecast from observed data, or mention that the stations are nearby reference points.
Define "without much help" in advance, such as no facilitator hints and a limit on how long they hesitate.
Recruit people who actually ski in Washington.
Include a return visit in the same browser to test "find it again."
Ask which of the five metrics they ignored or wished for, since that begins validating your assumptions.
If the two resorts are pre-selected, the "select two resorts" task becomes trivial, so adjust it. The selection step is still your weakest candidate to simplify.

If you resolve only two things before testing, make them what "save" stores and where each metric comes from. Those two decisions shape most of the other issues here.

Please review the sketches from a usability perspective. Focus on:

Visual hierarchy and information organization.
Whether users can easily understand the main actions.
Whether forecast data and observed snowpack data are clearly distinguished.
Whether important information, labels, and units are easy to find.
Any confusing or missing interface elements.

Please do not replace my sketches or generate a completely new interface. Give me specific feedback that I can use to refine my existing designs.
Separate essential improvements from optional suggestions.

Your sketches are consistent and easy to scan. Resort names work as column headers, labels sit on the left with values on the right, and putting the confirmation and saved list on one screen keeps the flow short. The main gap is that the screens are drawn but the controls that connect them are not.

Essential improvements

Across all three screens

Each screen needs a clear primary action. The home page has no "Compare" button, the comparison page has no "Save" button, and the saved page has no way to start a new comparison. As drawn, users can't move through your three actions. Add one primary button per screen. On the home page, keep "Compare" disabled until two resorts are selected.
Returning users can't find saved comparisons. They land on the home page, which has no link to "My Saved Comparisons." Your test task "find it again" would fail here. Add a persistent link from the home and comparison pages.

Mockup 1: Home page

Resort count doesn't match your MVP. Earlier you said the MVP covers Crystal and Stevens, but the sketch lists six resorts. If only two work, the other four are dead ends that damage trust. If all six work, you need station data for each, and the selection step becomes meaningful.
Selection rules are undefined. Checkboxes allow any number of selections. Decide what happens on a third check (disable the rest, or replace the oldest) and what happens with fewer than two. Also say whether Crystal and Stevens are pre-checked by default or just an example state.
"Select Date" is ambiguous. Label it as the trip date and decide the allowed range. Observed snow depth can only exist for today or earlier, so a future date like the Dec. 3 shown can't have an observed value for that day. Likewise, a past date has no forecast. Without a rule, users will see mismatched data.

Mockup 2: Comparison page

Forecast and observed are only partly distinguished. "Forecast Snowfall" and "Observed Snow Depth" are labeled, but Temperature and Wind Speed are not, so users must guess which they are. The order happens to group the rows, but nothing shows that. Add two visible groups with headings (for example, "Forecast for Dec. 3" and "Observed at nearby station") rather than relying on prefixes.
SWE is missing. It's in your list of five metrics but not in the sketch. Add it with a short label like "Snow water equivalent (SWE)", or update your metric list.
The station context you planned isn't shown. Add the station name and elevation under each resort name or in the observed group, plus an "as of" time for observed values. Without these, the nearby-reference-data disclosure doesn't exist in the design.
Units and value definitions need decisions.
Unit system: The sketch uses °C, km/h, and cm, but Washington recreational skiers typically think in °F, mph, and inches, as do resort snow reports and SNOTEL. Metric forces mental conversion in a task meant to be quick. Test this, but I'd default to US units.
Snowfall window: Specify it ("24 hr" or "on Dec. 3").
Temperature: Say what it is (high, low, or average) so users don't guess.
"Summary:" is undefined. Is it generated or written by the user? If generated, what does it say? This is where users expect the answer to "which is better?", but the metrics don't all point the same direction (wind and temperature in particular). A factual summary of differences is safer than declaring a winner.

Mockup 3: Saved comparisons

The card doesn't say what was saved. "Saved Resort Pair" suggests you're saving the pairing, not a snapshot, which settles my earlier question. But the date isn't on the card. Does "Compare Again" use the saved date, today, or ask again? Show the date (or state the rule) so users know what they'll get.
The trash icon is risky. It's unlabeled, sits next to the primary button, and local storage can't recover deleted items. Make it visually secondary and add a confirmation or undo.
Optional suggestions
Home page copy order: "Compare weather & snow condition" reads like a tagline tucked below the instruction. Consider the value statement first, then "Select two resorts." Also fix "conditions."
Selection feedback: Make the whole resort row tappable with a stronger selected state than a small checkmark, and consider a "2 of 2 selected" indicator.
Visual hierarchy on the comparison page: Make values the most prominent, labels secondary, and resort names strong headers. The date box in the corner looks like a button, so make clear whether it's editable.
Label column width: "Observed Snow Depth" runs into the divider. Give labels more room or let them wrap.
Summary placement: At the bottom, it may fall below the fold on a phone. Consider whether users will see it.
After saving: Highlight the newly saved item, especially once multiple comparisons exist. Add an empty state for first-time visits and decide how duplicate pairs are handled.
Local storage note: A short "Saved in this browser" line near the confirmation, as I mentioned earlier.
Naming and typos: "Crystal Mt." versus "Crystal Mountain," "Steven Pass" on the home page, and "Comparesion Saved!" in the confirmation. Pick one name per resort and use it everywhere.
"Compare Again": It works if it fetches fresh data. A hint like "latest conditions" would reinforce that.

These are judgments from pencil sketches, so I can't assess color, size, or contrast. If you only have time for a few fixes before testing, start with the missing buttons and navigation (1, 2), the forecast and observed grouping with date rules (5, 6), and what the saved card stores (11).


I used AI suggestions to help review and refine my existing UX work, including:
- Feedback on the user flow and interaction sequence.
- Suggestions for missing user needs or usability considerations.
- Feedback on consistency between the persona, user journey, and proposed features.
- Suggestions for improving the clarity of mockup descriptions and proposal content.

**Files or sections affected:**
- `P2/p2.md` — Sections 1–3
- `P2/p2.md` — Section 7
- `P2/p2.md` — People criteria in Section 8
- `P2/mockups/`

### 4. Review and Verification

I reviewed AI-generated suggestions before incorporating them into the project.

- I compared suggestions with our original project requirements and user needs.
- I checked that the user flow remained consistent with the features we had independently defined.
- I reviewed the persona and user journey to ensure they reflected our intended target audience.
- I compared the mockups with the written interaction descriptions to identify inconsistencies.
- I accepted, modified, or rejected suggestions based on their relevance to the project.

### 5. Understanding and Reflection

Using AI helped me review my UX work from another perspective and identify details that I might have overlooked. It was useful for checking the clarity of the user flow and consistency between the persona, user journey, and mockups.

However, I developed the initial product ideas and design materials myself. AI feedback was only used to refine existing work. This helped me understand that AI can be useful for identifying potential issues, but the final design decisions should remain grounded in our own research, project requirements, and judgment.

---

## Member B — Technical & Data (Ruihan Gao)

### 1. AI Use Overview

**AI tools used:** Claude

**Purpose of AI use:**

I was responsible for the technical and data aspects of Snow Compare. I used Claude as a supporting tool for API research, data organization, and technical proposal review.

My AI-assisted tasks included:
- Reading and understanding the Open-Meteo and USDA NRCS AWDB API documentation.
- Understanding the distinction between the NRCS AWDB REST API and the SNOTEL station network.
- Organizing and formatting JSON examples based on actual API responses.
- Reviewing the technical descriptions and checking for missing details or inconsistencies.
- Getting feedback on the data model, project structure, and technical risks that I had independently planned.

I made the initial technical decisions and independently ran the API requests. AI was used to help explain, organize, and review my work rather than to determine the project's core requirements or data model.

### 2. Specification Before Prompting

#### Task 1: API Research and Documentation

**Task / Feature:** Understand and document the APIs used by Snow Compare.

**Expected behavior:**
- Inputs: Official API documentation, request parameters, station identifiers, and actual API responses.
- Expected outputs: Accurate explanations of the API endpoints, parameters, returned fields, and their roles in the project.
- Constraints: Distinguish forecast data from observed snowpack measurements. Use actual API responses as the source of truth.

**Checks:**
1. Verify that API endpoints and request parameters match the actual requests.
2. Compare documented response fields and values against actual API responses.
3. Ensure that the descriptions correctly distinguish the AWDB API from the SNOTEL network.

#### Task 2: JSON Evidence Organization

**Task / Feature:** Organize actual API responses into readable JSON evidence files.

**Expected behavior:**
- Inputs: Actual Open-Meteo and NRCS AWDB API responses.
- Expected outputs: Valid JSON files containing the relevant response data.
- Constraints: Preserve relevant field names, dates, units, station identifiers, and observed values. Do not invent API data.

**Checks:**
1. Validate that the resulting files contain valid JSON syntax.
2. Compare selected values with the actual API responses.
3. Confirm that data fields and units are consistent with the API documentation.

#### Task 3: Technical Proposal Review

**Task / Feature:** Review the technical proposal and identify missing details or inconsistencies.

**Expected behavior:**
- Inputs: My independently developed technical plan, API evidence, data model, and project requirements.
- Expected outputs: Suggestions for improving technical clarity and identifying potential gaps.
- Constraints: Preserve our independently established project requirements and technical decisions. Do not present planned functionality as already implemented.

**Checks:**
1. Check that API descriptions match the evidence in Section 4.
2. Check that the data model and project structure are consistent across Sections 5 and 6.
3. Check that technical limitations and station-mapping uncertainty are accurately described in Section 9.

### 3. AI Prompts and Generated Output

**Prompts and full transcripts:**
I am working on a UW HCDE 310 project called Snow Compare.
Our project compares ski resort conditions in Washington State using two data sources:

Open-Meteo API: Provides weather forecasts, including snowfall, temperature, precipitation, and wind speed.
USDA NRCS Air and Water Database (AWDB) REST API: Provides snowpack observations from SNOTEL stations, including:
SNWD: Snow depth
WTEQ: Snow-water equivalent

Our MVP supports Crystal Mountain and Stevens Pass.
We have independently researched the APIs and tested actual requests. I will provide our current API descriptions and example responses below.
4. Data sources — Member B
Source 1: Open-Meteo Forecast API

Documentation: https://open-meteo.com/en/docs
Action/step: Action 2, steps 1–3. Request forecast snowfall, maximum temperature, and maximum wind speed using each selected resort's coordinates.
Key/limits: The standard free non-commercial Forecast API does not require an API key. The free tier allows up to 10,000 API calls per day. Attribution is required under the CC BY 4.0 license. The application should handle timeouts, HTTP errors, and missing forecast values.
Example request:
https://api.open-meteo.com/v1/forecast?latitude=46.93&longitude=-121.50&daily=snowfall_sum,temperature_2m_max,wind_speed_10m_max&timezone=America%2FLos_Angeles&forecast_days=3
One real trimmed response (from our previous test):
{
  "daily": {
    "time": [
      "2026-11-22",
      "2026-11-23",
      "2026-11-24"
    ],
    "snowfall_sum": [0.0, 2.17, 2.94],
    "temperature_2m_max": [29.5, 35.6, 34.4]
  }
}

The tested temperature values were returned in °F. Snowfall was returned in cm. The response also included daily wind speed, but its exact values should be copied from the saved API response before including them here.
* What surprised us: Open-Meteo returns a forecast for the requested geographic coordinates rather than an official resort-specific forecast. The returned grid coordinates and elevation can differ from the coordinates and elevation supplied in the request. We should therefore display the forecast location and avoid presenting it as an exact measurement at every part of the resort.

Source 2: USDA NRCS SNOTEL via AWDB

Documentation/official links:
https://wcc.sc.egov.usda.gov/awdbRestApi/swagger-ui/index.html
https://www.nrcs.usda.gov/programs-initiatives/sswsf-snow-survey-and-water-supply-forecasting-program
Action/step: Action 2, steps 1–3. Retrieve snow-depth observations and, when available, snow-water equivalent (SWE) from a nearby SNOTEL station.
Key/limits: The AWDB REST API provides station metadata and time-series observations. The application must handle unavailable stations, missing elements, stale observations, and differences in observation timestamps. Station metadata should be checked before associating a station with a resort.
Real endpoint/call with parameters:
https://wcc.sc.egov.usda.gov/awdbRestApi/services/v1/data?stationTriplets=642:WA:SNTL&beginDate=2026-11-14&endDate=2026-11-21&elements=SNWD,WTEQ&duration=DAILY
This request was tested for station 642:WA:SNTL.
One real trimmed response (from our previous test):
{
  "stationTriplet": "642:WA:SNTL",
  "observations": {
    "SNWD": [6, 8, 8, 5, 8, 10, 10, 12],
    "WTEQ": [2.7, 2.8, 2.9, 2.9, 3.0, 3.2, 3.1, 3.2]
  },
  "unit": "inches",
  "dates": [
    "2026-11-14",
    "2026-11-15",
    "2026-11-16",
    "2026-11-17",
    "2026-11-18",
    "2026-11-19",
    "2026-11-20",
    "2026-11-21"
  ]
}

SNWD represents snow depth, while WTEQ represents snow-water equivalent. Both values were returned in inches in this test.
* What surprised us: The station data is reported in inches, so the application needs unit conversion before displaying values alongside other data. Also, a successful observation request does not by itself provide all the station metadata needed for a resort comparison. We still need to verify the station name, coordinates, elevation, and distance from each resort.

Integration rule: For each supported resort, associate a verified nearby SNOTEL station with its station ID, distance, elevation, and observation timestamp. Clearly label the data as “nearby SNOTEL station — not resort report.” A fixed, verified station mapping is acceptable for the P3 MVP if automated station discovery adds too much scope. Do not assume that station 642:WA:SNTL is suitable for Crystal Mountain or Stevens Pass until its metadata and distance have been checked.
Please review our API research and identify:

Any incorrect terminology or misunderstandings about the two APIs.
Any missing request parameters or important response fields.
Potential issues when matching ski resorts to nearby SNOTEL stations.
Potential problems with units, timestamps, missing values, or unavailable observations.
Whether our selected data fields are sufficient for the proposed MVP.

Do not invent API response values or assume that station mappings are verified. Clearly distinguish confirmed facts from recommendations or uncertainties.
Please organize your review into:

Issues found
Missing considerations
Recommended checks
Review of Snow Compare API research

I did not re-run either API or check the live docs while writing this. Each item is tagged:

[Your data]: directly visible in what you pasted.
[Recall]: from my general knowledge of these APIs, which you should verify in the docs or a saved response.
[Rec]: my recommendation.

I did not look up any SNOTEL station metadata, so I am not proposing specific stations for either resort.

1. Issues found

Open-Meteo

The request doesn't match the response units. [Your data + Recall]
Your example URL has no temperature_unit parameter, but you report °F.
As I recall, Open-Meteo's defaults are °C, km/h and mm, with snowfall in cm.
Values like 29.5 and 35.6 would be implausible in °C for Crystal in late November, so the test probably used temperature_unit=fahrenheit, or the URL was trimmed.
Your documented request needs to be the exact one that produced the saved response.
The trimmed response drops fields that matter. [Your data]
It omits daily_units and the top-level latitude, longitude, elevation, timezone and utc_offset_seconds.
You already say the returned grid location can differ from the requested one, and those top-level fields are where you'd see it. Save and quote them.
The wind field is also missing. You already flagged that its values need to be copied from the saved response.
"Forecast for the requested coordinates" needs refining. [Rec]
It is gridded and downscaled model output, not a measurement and not an official resort or NWS forecast.
Snowfall is a modeled estimate. In steep terrain it can be off, especially around the rain/snow line.
Your instinct to display the forecast location is right.
The "10,000 calls/day" limit is incomplete. [Recall]
I believe the free tier also has per-minute and per-hour caps and is for non-commercial use only. Verify on Open-Meteo's terms page.
The 10,000/day figure is fine for the MVP, but cite the terms page, not just the number.

AWDB / SNOTEL

Your trimmed AWDB response may not be the raw shape. [Recall]
As I recall, /data returns an array of station objects. Each has a stationTriplet and a data array of elements, and each element has a stationElement block (element code, duration, stored unit, etc.) and a values list of {date, value} objects.
Top-level observations, unit and dates arrays look like something your team reshaped.
Compare against the raw saved response and the Swagger schema. Document the raw shape as the "real response" and describe your normalized shape separately.
Units are asserted but not sourced. [Your data]
"Inches" appears as a top-level unit. If that field isn't in the raw response, the unit should come from the element metadata (stored unit code) instead.
The SWE-to-depth ratio in your sample deserves a plausibility check. [Your data]
At the start of the range, 2.7 in SWE over 6 in depth implies about 45% density, which is unusually dense for early-season snow. Later days look more typical (about 27%).
This may be real (wet or compacted early-season snow) or a sensor/QC artifact. Don't treat it as wrong, but don't build logic that assumes the values are clean.
Station 642 is not yet associated with anything. [Your data]
You already note this. I am not asserting what 642 is or where.
2. Missing considerations

Request parameters and response fields

Open-Meteo, optional parameters [Recall/Rec]:
temperature_unit, wind_speed_unit and precipitation_unit. I believe precipitation_unit=inch also switches snowfall to inches, which would avoid manual conversion; confirm via daily_units.
elevation, to override the elevation used for temperature downscaling, since resort base and summit differ by thousands of feet.
past_days, to line up recent forecast-model days with the SNOTEL window.
models, if you want to control or disclose which model is used.
Open-Meteo, extra fields worth considering [Rec]:
temperature_2m_min
precipitation_sum, to tell rain from snow
wind_gusts_10m_max
weather_code
Hourly freezing_level_height, which is highly relevant in the PNW
Max temp alone says little about snow quality.
Wind is at 10 m, not at the summit. [Recall] Label it accordingly.
AWDB metadata endpoint [Recall]:
The station metadata endpoint (/services/v1/stations) provides name, latitude, longitude, elevation (I believe in feet), network, and begin/end dates.
You need these for station verification.
AWDB data parameters [Recall, verify in Swagger]: options such as returnFlags, periodRef, centralTendencyType and activeOnly. Quality flags matter for deciding whether to display a value.
AWDB limits are blank in your write-up. Record whether a key is required (your test worked without one, which you can state as observed) and the rate limits (unknown, as far as I can tell).

Matching resorts to stations

Three different locations are in play: the resort, the Open-Meteo grid point, and the SNOTEL sensor. Show all three, not just distance to the station.
Elevation difference often matters more than horizontal distance. A station 5 miles away but 2,000 ft higher or lower than the ski terrain can behave very differently. Compare station elevation to resort base, mid and summit, using official resort figures, not memory.
Aspect and terrain: a station on the other side of a ridge or pass may be a poor proxy even if close.
Multiple candidate stations per resort. Decide your tie-break rule (closest, closest in elevation, or a weighted score) and document it.
Station status: inactive, discontinued, or sensor-less stations (e.g., no SNWD) should be excluded when you pick the fixed mapping.
Naming: a station named after a pass or lake can be misleading. Do not infer suitability from the name.
Distance method: use great-circle (haversine) distance from the metadata coordinates, and record which resort reference point you used.

Units, timestamps, missing data

Four unit systems to reconcile: °F (as tested), cm (snowfall), inches (SNOTEL), and wind (default km/h unless changed). Pick one display system, probably US units, and convert in one place. Inches to cm is ×2.54.
Different quantities: forecast snowfall_sum (new snow) is not comparable to SNOTEL SNWD (accumulated depth) or WTEQ (water content). Present them side by side but never subtract or sum them.
Timestamps [Recall, verify]:
SNOTEL daily values are reported for a calendar date, and I believe the daily value reflects a reading near the start of that day in Pacific Standard Time.
Open-Meteo daily values are local calendar days using the timezone you request (DST-aware).
Your sample ends 2026-11-21 and the forecast begins 2026-11-22, so the observation was at least a day old when forecast data started.
Missing or stale observations:
Open-Meteo returns null entries in arrays for missing values.
For AWDB, expect missing days or an absent element entirely (for example no WTEQ).
Define a staleness threshold, e.g. "latest observation older than N days shows 'stale'".
Zero versus missing: early season, 0 snow depth is a legitimate value. Don't render it as "no data".
Provisional data: I believe SNOTEL data are provisional and subject to revision, so a disclaimer is advisable.
Error handling: Open-Meteo returns a JSON error body (I recall error: true with a reason) on bad requests. Handle that separately from timeouts and HTTP failures.
Browser access [Uncertain]: if calls are made from client-side JavaScript, check whether AWDB sends CORS headers. If not, you'll need a small proxy or server-side fetch.
3. Recommended checks
Re-run and save both raw responses, with full URL, timestamp and headers. Replace the "trimmed" examples with the raw shape plus your normalized shape.
Open-Meteo:
Re-run with explicit units and record daily_units and the top-level lat/lon/elevation for both resorts.
Copy the real wind values from that response.
Check how many nulls appear in the 3-day window.
AWDB metadata:
Query station metadata for Washington SNTL stations and filter to those near each resort.
Record for each candidate: station triplet, name, latitude, longitude, elevation, network, begin/end dates, and whether SNWD and WTEQ are available.
Pick and document the mapping.
For each resort, compute distance and elevation difference to the candidates.
Choose one, and write down the rule and why.
Keep station 642 only if it passes this check.
Check the latest observation.
Request a window covering the last few days and confirm how the latest date, the flags and the missing days appear.
Test a station or element you expect to be missing to see what the API actually returns.
Confirm the terms and limits on the Open-Meteo terms page and the NRCS docs, and note the attribution wording you'll display.
Check the data against a second source, e.g. SNOTEL's own station page or the resort's published report, to catch sensor oddities like the 45% density value.

Are your selected fields sufficient for the MVP? Mostly yes for a bare-bones comparison: forecast snowfall, max temperature and max wind, plus SNWD and WTEQ. I'd call it sufficient only if you also capture:

Forecast grid location and elevation.
Station name, elevation, distance and observation date.
daily_units.
A missing/stale indicator.

I'd add min temperature, precipitation sum and wind gusts if scope allows, since they make the comparison much more useful for actual ski decisions.

That makes sense. Our current Section 4 hasn't been updated with these details yet. Can you help me figure out exactly what we should add to Section 4?
Please keep the MVP scope simple. I don't want to add unnecessary features.

What to add to Section 4

I haven't verified anything new here. Items marked TBD need your team's saved responses or a docs check, and I've left them blank rather than guessing.

Open-Meteo: add these
The exact request that produced your saved response.
If you used Fahrenheit, add temperature_unit=fahrenheit.
I'd also add wind_speed_unit=mph and precipitation_unit=inch, so everything displays in US units without manual conversion. TBD: re-run and confirm snowfall comes back in inches. Check daily_units rather than assuming.
Fields the app reads: daily.time, snowfall_sum, temperature_2m_max, wind_speed_10m_max, plus the top-level latitude, longitude, elevation and daily_units. The top-level fields are what let you show the forecast location, which your "what surprised us" note already calls for.
Real wind values from the saved response (TBD), replacing the placeholder.
Missing-value rule: a null in any daily array displays as "no forecast data". Don't treat it as 0.
Attribution text you'll show (CC BY 4.0), and a link to the terms page. Add "non-commercial use" to the limits line.
UI label: "Forecast for grid point near [resort], modeled, not an official resort forecast."
SNOTEL / AWDB: add these
A second call, station metadata. Your data call alone can't verify a station. Add the stations endpoint with the fields you need: triplet, name, latitude, longitude, elevation, and begin/end dates. TBD: confirm exact field names and the elevation unit in Swagger.
Raw versus normalized response. Paste the raw saved response as "real response." If your current example is reshaped (I suspect it is), label it "our normalized shape."
Where the unit comes from. Cite the field in the raw response, or state that you confirmed inches from the docs or element metadata.
Freshness and missing rules:
The app displays the latest non-null SNWD and its date.
If WTEQ is missing, show SNWD only.
If the latest value is older than a threshold you choose (e.g. 3 days), show "stale".
Keep 0 distinct from missing.
The fixed mapping table (see below). This replaces any hint of automated discovery.
Limits line: state "no key required (observed in our test)" and "rate limits: TBD."
Mapping table to add
Resort	Station triplet	Station name	Station elev.	Distance	Verified date
Crystal Mountain	TBD	TBD	TBD	TBD	TBD
Stevens Pass	TBD	TBD	TBD	TBD	TBD

Under it, put one sentence on the selection rule, such as "closest active station with SNWD and WTEQ, then compared on elevation." Also list the resort reference elevations you used and their source. Note that station 642 is untested for either resort.

Deliberately leave out

Keep these out of Section 4 and, if you like, list them under "future work":

Min temperature, wind gusts, freezing level and weather codes.
past_days and the elevation override.
Automated station discovery or multiple stations per resort.
Quality-flag handling beyond checking for nulls.
Any attempt to blend forecast snowfall with SNOTEL depth. Show them side by side, labeled as different quantities.

OK, I will refine section 4 and here is our current technical plan and risk analysis:

## 6. Tech Plan — Member B

We plan to build Snow Compare using Python and Flask. The application will retrieve forecast data from the Open-Meteo API and snowpack observations from the USDA NRCS AWDB REST API. We will organize the project into separate modules for API requests, data processing, and application routes so that each part can be tested independently.

### Planned Project Structure

| File | Responsibility |
|---|---|
| `app.py` | Runs the Flask application and defines the main application routes |
| `open_meteo.py` | Requests weather forecast data from the Open-Meteo API |
| `nrcs.py` | Requests snow depth and snow-water equivalent observations from the NRCS AWDB API |
| `resorts.py` | Loads supported resorts and their selected nearby SNOTEL station mappings |
| `data/resorts.json` | Stores resort coordinates and selected nearby-station metadata |
| `templates/index.html` | Displays the main resort comparison interface |
| `static/style.css` | Defines the visual layout and styling |
| `static/script.js` | Handles client-side interactions, including resort selection and saved comparisons |

### Data Processing Plan

1. Retrieve forecast data for each selected resort using its latitude and longitude.
2. Retrieve daily snow depth (`SNWD`) and snow-water equivalent (`WTEQ`) observations from the corresponding SNOTEL station through the NRCS AWDB API.
3. Normalize the returned data into consistent structures for display.
4. Clearly label forecast dates, observation dates, units, and station locations so users can distinguish forecasted conditions from measured snowpack.
5. Handle API errors and missing observations gracefully, displaying an informative message instead of causing the application to fail.

We will keep the API request logic separate from the Flask routes and user interface. This structure will make the application easier to debug, test, and extend.
## 9. Priorities and risks — Member B, reviewed with A

**Must-have (ordered):**

1. Validated selection of two different resorts.
2. Open-Meteo forecasts for both selected resorts.
3. A selected nearby SNOTEL station mapping for each resort, with an honest unavailable-data state if no suitable station or observation is available.
4. AWDB observation requests with graceful handling of missing or stale measurements.
5. A clear side-by-side Many Lenses display that distinguishes forecasts from nearby station observations and shows relevant source information.
6. JSON-based saving and reloading of resort pairs.
7. Three accessibility checks: visible labels and error messages, keyboard navigation with visible focus, and information that does not rely on color alone.
8. A runnable README and safe `.env` handling in P3.

**Nice-to-have (highest priority first):**

1. Visual charts for comparing snowfall and weather trends.
2. Support for additional Washington ski resorts.
3. A longer forecast date range.
4. Optional personalized weighting of weather and snow conditions.

Features will be cut from the bottom of this list if development time is limited.

**Risks and early tests:**

1. **Station coverage mismatch:** Nearby SNOTEL stations may be located at different elevations or may not fully represent conditions across a ski resort. Our initial tests identified Morse Lake (`642:WA:SNTL`, 5,400 ft) as the selected station for Crystal Mountain and Stevens Pass (`791:WA:SNTL`, 3,940 ft) as the selected station for Stevens Pass. Early test: use the resort and station coordinates to calculate their distance, compare their elevations, and review the available observation dates and values. These checks provide context for interpreting the station measurements but do not establish that a station represents conditions across the entire resort. The app will identify the station and its location context clearly. If a station is unavailable or unsuitable, the app will display an unavailable-data state rather than presenting an unrelated measurement as resort conditions.

2. **Data mismatch or API outage:** Forecast dates may not align with observation timestamps, or an external service may return missing data, stale measurements, or an error. Early test: inspect actual API responses, compare their timestamps and units, and test missing-data and API-failure cases. Verify that the app labels each data source and time period correctly and preserves any successfully retrieved data when the other source fails.

Please review our plan and identify:

Whether the module responsibilities are clearly separated.
Potential problems with API failures, slow responses, and missing data.
What should happen when a SNOTEL station has no recent observations.
Potential problems with units, dates, and time zones.
Whether our proposed project structure is unnecessarily complicated or missing important components.
Any risks that we have overlooked for the MVP.

Please distinguish essential requirements from optional improvements. Do not write implementation code. We are currently planning the architecture, not implementing the application.

Review of Section 6 (Tech Plan) and Section 9 (Priorities and Risks)

I haven't verified any station metadata or re-run either API. Tags: [Essential] for the MVP, [Optional] if time allows, [Recall] for my general knowledge of the APIs, which you should confirm in docs or saved responses.

1.

The plan separates API requests, data, and routes well, and keeping fetch logic out of the Flask routes is the right call. These gaps remain:

[Essential] Normalization has no home. Data Processing step 3 says to normalize the returned data, but no file owns it, so it will likely end up in app.py or inside the fetch modules. Decide one place for it: a small processing module, or the fetch modules returning already-normalized results. Either works, but pick one.
[Essential] Something has to combine the two sources. For each resort, someone must call both modules, label the pieces, and build the status for each. If that happens in the route, app.py stops being a thin layer. A single "build comparison for a resort" function (in a processing module or app.py) is enough. No new layer is needed.
[Essential] Saved comparisons are ambiguous. script.js handles "saved comparisons," and Section 9 says "JSON-based saving and reloading of resort pairs." Does that mean browser storage or a JSON file written by Flask? These have very different consequences (see section 6). Decide now.
[Essential] Keep both API calls server-side. This also settles the CORS question I raised earlier: if only Flask calls Open-Meteo and AWDB, CORS doesn't matter. Say explicitly that script.js never calls either API directly.
[Essential] Unit and date conversion needs one owner. Right now it's unassigned (see section 4).
resorts.py and data/resorts.json are fine, and the split is reasonable. resorts.json should hold more than coordinates and a station ID (see section 5).
2. API failures, slow responses, missing data
[Essential] Explicit timeouts on every outbound request, with a decision on the value. I don't know AWDB's typical latency, so measure it during your tests. Without timeouts, one slow service hangs the whole page.
[Essential] Four outbound calls per comparison (two forecasts, two station requests). If they run sequentially, worst-case wait is the sum of all timeouts. Keep timeouts short enough that this is tolerable.
[Essential] Give each source its own result status, separate from its data. At minimum:
OK
fetched but no usable values
stale
request failed (timeout, HTTP error, malformed response)
This is what makes your Risk 2 requirement possible: preserving the successful source when the other fails. It also lets the UI say "couldn't reach the service" versus "the station has no data," which are different messages.
[Essential] Treat a malformed or unexpected response as a failure, not a crash. That includes the Open-Meteo JSON error body, an empty AWDB result, and a missing element such as no WTEQ.
[Essential] Nulls are not zeros. This applies to both sources, and 0 snow depth is a legitimate value early or late in the season.
[Optional] Simple caching (e.g., a few minutes to an hour). SNOTEL daily values don't change within the day, so caching would speed up repeat loads and reduce calls. At your scale, 10,000 calls/day is unlikely to be the problem, so skip it unless you see slow loads.
[Optional] Batching. I recall that both APIs accept multiple locations or stations in one request (Open-Meteo via comma-separated coordinates, AWDB via comma-separated stationTriplets). Confirm in the docs if you want to halve your call count. It isn't needed for the MVP.
[Optional] Retries. Skip them. A clear error message is simpler and enough for the MVP.
3.

Your Section 9 says the app shows an "honest unavailable-data state," but the plan doesn't define when a station counts as stale versus unavailable. I'd define the cases below. The thresholds are your decision, and I'm not asserting what's typical.

Situation	Suggested display
Latest non-null value is within your freshness threshold	Show it with its observation date
Latest non-null value is older than the threshold but inside your lookback window	Show it, clearly labeled stale, with its date
No non-null values in the whole lookback window	Show "no recent observation from this station" and no numbers
SNWD present, WTEQ missing	Show depth only, and say water equivalent is unavailable
Value is 0	Show 0 as a real value, not "no data"
Request failed entirely	Show a service-error message, distinct from "no observations"

Further rules to settle:

[Essential] Never substitute. Don't fall back to another station or fill the gap with forecast data. That would contradict your own "not resort report" labeling.
[Essential] Make the lookback window long enough to find a recent value after gaps. Your test used 8 days. Pick a number and document it.
[Essential] Decide how to handle SNWD and WTEQ having different latest dates. Show each with its own date, or only show values sharing a date.
[Optional] Off-season message. In summer, a station reading 0 or null is expected, and "snow-free at station" is a better message than "no data." This matters little for a fall/winter class demo but is worth a line in the README.
4.
[Essential] Convert units in one place and decide the display system. Four sources of mismatch are in play:
Temperature: confirm the request parameter.
Snowfall: cm by default, or inches if you set precipitation_unit.
Wind: default units unless you set a parameter.
SNOTEL: inches.
[Essential] Elevation units differ. [Recall] Open-Meteo returns elevation in meters, while SNOTEL station elevations are typically reported in feet. Your Section 9 uses feet for stations. When you show the forecast grid elevation next to the station elevation, convert one so they match. Confirm both units in the saved responses.
[Essential] Compute "today" in Pacific time, not server time. Your AWDB beginDate/endDate are date strings. If the Flask host runs on UTC, the end date can be wrong or in the future for part of each evening. Anchor date logic to America/Los_Angeles.
[Essential] Treat dates as plain date strings, not timestamps. Both APIs return calendar dates. Be careful in script.js: JavaScript's new Date("2026-11-22") parses date-only strings as UTC and can display the previous day in Pacific time. This is a common bug.
[Essential] Don't compare the two data series as if they share a time basis. Observations are past days, and the forecast is future days, and your earlier test already showed a gap (observation ended 11-21, forecast began 11-22). Label both clearly, as your Data Processing step 4 intends. Also decide whether the forecast's current day (partially elapsed) is labeled as such.
[Recall, verify] SNOTEL daily timing. I believe daily values reflect a reading near the start of the calendar day, which affects how you describe "as of" in the UI. Confirm in NRCS documentation before wording the label.
[Essential] Keep raw values and rounded display values separate. Convert first, round only for display, and be consistent about decimals.
5. Structure: too complicated, or missing pieces?

It is not too complicated. Eight files for a Flask app is reasonable. I would not simplify further. These are missing:

[Essential] A tests location, with saved real API responses as fixtures. Your Risk 2 early tests (missing data, API failure) are hard to run against live services, so you need saved or fake responses. This also matches the earlier recommendation to save raw responses.
[Essential] requirements.txt and the README, which Section 9 already requires.
[Essential] More fields in resorts.json: station triplet, station name, station elevation, distance, date verified, the resort reference point used, and the resort elevation source. Without them you can't show "station and location context" the way Section 9 promises.
[Essential] .env and the API keys question. Neither API needs a key in your tests, so what would .env hold? Possibly only a Flask secret or config. Section 9 says "safe .env handling," which implies secrets. Either name the secret or drop the requirement so it doesn't become unexplained scope.
[Optional] A minimal logging or debug approach for failed API calls. Even printed messages help a team debug during P3.
[Optional] A short error-message list (copy for each status) so wording stays consistent.
6. Overlooked risks
[Essential] Section 9 and Section 4 disagree. Section 9 says your tests "identified" 642:WA:SNTL (Morse Lake, 5,400 ft) for Crystal Mountain and 791:WA:SNTL (3,940 ft) for Stevens Pass. Your earlier Section 4 says 642 hasn't been checked. I have not verified any of these station details or distances. Before the proposal calls the mappings verified, record the evidence in resorts.json, with the date, and make every section say the same thing. The elevation comparison should use official resort base/summit figures, not memory. Section 9's own early test (distance, elevation, observation dates) is the right check, so make sure it's actually done and the results are saved.
[Essential] Attribution and non-commercial terms are not in the must-haves. Open-Meteo requires CC BY 4.0 attribution, so the display needs it. Add it to must-have 5 or to the README checklist.
[Essential] Saved pairs need validation. If saved pairs live in a Flask-written JSON file, handle a missing or corrupted file, reject resort IDs not in resorts.json, and think about concurrent writes. With no accounts, a server file is shared by all users, which may not be what you want. If it's browser storage, say so, and handle empty or corrupted storage. Either way, validate on load.
[Essential] "Two different resorts" is validated server-side, not only in the UI.
[Optional] Station reuse across resorts. If two resorts ever map to the same station, the comparison would be misleading. Not a problem with your current two, but worth a check in the data file validation when you add resorts.
[Optional] A one-line disclaimer that the app is not for safety or avalanche decisions. It's cheap and appropriate given how it could be read.
[Optional] Provisional data. I believe SNOTEL data are provisional and subject to revision (verify), so one line of disclaimer is enough.

I used Claude to help:
- Explain the roles of Open-Meteo, the NRCS AWDB API, and SNOTEL stations.
- Clarify API request parameters and response structures.
- Format selected API response data into readable JSON examples.
- Improve the wording of technical descriptions for the data model and project structure.
- Identify inconsistencies in terminology and technical claims across proposal sections.
- Suggest potential technical risks and missing considerations.

**Files or sections affected:**
- `P2/p2.md` — Section 4: API Research
- `P2/p2.md` — Section 6: Tech Plan
- `P2/p2.md` — Section 9: Priorities and Risks
- `P2/evidence/open_meteo.json`
- `P2/evidence/snotel.json`
- `P2/evidence/stevens_pass_snotel.json`

### 4. Review and Verification

I reviewed AI-generated content before incorporating it into the project.

- I independently ran API requests and used the returned data as the source of truth.
- I compared JSON examples against actual API responses to check field names, dates, units, and values.
- I checked the Open-Meteo evidence against the forecast response and the NRCS AWDB evidence against the corresponding SNOTEL station responses.
- I revised technical explanations when AI-generated wording overstated the certainty of station mappings or other technical details.
- I checked the relationship between the AWDB API and SNOTEL network to ensure that the proposal describes the API and data source accurately.
- I reviewed the technical sections together to maintain consistency between API evidence, the data model, implementation plan, and identified risks.

### 5. Understanding and Reflection

Using Claude helped me understand API documentation, organize technical information, and improve the clarity of the proposal. It was particularly useful for clarifying the relationship between the NRCS AWDB API and SNOTEL stations, structuring API response examples, and identifying inconsistencies across technical sections.

However, I did not rely on AI to define the project's problem, audience, data model, or success criteria. I established the initial technical direction myself and used actual API requests and documentation to verify AI-assisted explanations and examples.

This process reinforced the importance of treating AI output as a suggestion rather than an authoritative source. I remained responsible for checking data fields, units, station identifiers, timestamps, and technical claims.

In future implementation work, I may use AI to help develop API request functions and error handling. However, I will first define the expected behavior and checks, then review and test generated code against the project specifications, including missing data, invalid input, and network failures.

