I’m developing some concept to build a APP, Concept 2, Snow Compare would be more like existing forecasting software, such as OpenSnow. It provides users with weather conditions, like snowfall amounts, wind speed, humidity, and temperature, and then lets users decide for themselves the best time and location to go based on the available information. It would also make it easier to compare conditions across different ski resorts. Do you have some advices?

Here’s my take on Snow Compare. The idea is solid, but OpenSnow is well established, so the main question is what makes yours worth switching to.

Make comparison the core, not a feature
OpenSnow has comparison tools, but they’re secondary to its forecasts and human-written daily snow reports. If comparison is your whole identity, you can build a much better experience around it:

Side-by-side view of 2 to 5 resorts with a time slider, so users see how conditions change hour by hour or day by day.
A “best day / best resort” ranking for a date range (e.g., “this weekend, which of these five is best?”).
A visual heat-map or timeline view, where users can spot the best window at a glance instead of reading tables.

Personalize the ranking
Letting users “decide for themselves” works best if you let them define what “best” means:

Sliders or presets: powder hunter, groomer cruiser, sunny spring skiing, avoiding wind.
Ski vs. snowboard, skill level, and pass type (Epic, Ikon, Mountain Collective, or local season passes).
Drive time or distance from home, since a slightly worse resort that’s an hour closer often wins.

Go beyond raw numbers
Snowfall, wind, humidity, and temperature are table stakes. The more useful signals are derived ones:

Elevation-specific forecasts (base, mid, summit), since the same storm can be rain at the base and snow up top.
Freezing level and rain risk, plus snow-to-liquid ratio as a proxy for powder quality.
Wind-hold or lift-closure risk, which matters a lot for real-world planning.
Model confidence: when forecast models disagree, show a range rather than a single number. This builds trust and is something many apps skip.
Live resort data like lifts open, base depth, and webcams, so forecasts sit next to ground truth.

Data sources and costs

Weather: NOAA models (GFS, NAM, HRRR), ECMWF, or commercial APIs like Open-Meteo, Tomorrow.io, or Meteomatics. Check licensing, since some free tiers prohibit commercial use.
Snow data: SNOTEL stations, resort snow reports, and third-party feeds. Resort data can be messy and inconsistent, so budget time for cleaning it up.
API costs scale with users and with the number of locations and elevations you query, so model this early.

Scope your MVP tightly
Launch in one region (say 20 to 30 resorts) rather than nationwide. You’ll deliver a better product, validate demand faster, and keep data costs down. A PWA or simple cross-platform app (Flutter or React Native) is enough to test the concept before investing in native builds.

Monetization

Freemium: free for basic comparison of a few resorts, paid for extended forecasts, more resorts, alerts, and personalization.
Affiliate revenue from lift tickets, passes, lodging, and gear.
Push alerts (“5+ inches expected at any of your saved resorts”) are a strong retention and conversion driver.

Risks to plan for

Seasonality: usage drops sharply in summer, so think about subscription pricing and off-season features (e.g., Southern Hemisphere, trip planning).
Trust: people blame the app when a forecast busts. Showing sources and uncertainty helps.
Competition: OpenSnow, plus general weather apps and resort apps. Your edge needs to be clear in one sentence.

If you tell me who you’re building this for (local day-trippers, destination travelers, or pass holders) and which region you’d start in, I can help sharpen the feature list and sketch an MVP roadmap or wireframe.

For Concept 3, after discussion we think collecting public APIs from various websites is a bit unrealistic, so for the third one we want to change it to an introduction for snowboarding beginners — recommending suitable snowboard equipment for them, such as bindings, boots, and boards, based on their different riding styles and the progression path they want to take in the future.

Dropping the API scraping is a good call. This version also plays to your strengths: it’s mostly curation and domain knowledge rather than data plumbing.

Recommend specs first, products second
Beginners don’t need “buy the Burton Custom.” They need to know what to look for. Have your engine output a gear profile (e.g., “soft-to-medium flex, true twin, hybrid camber, 155 cm”) and then show a few example products that match. This stays useful when models change each season, and you only have to maintain a small curated catalog.

Build the recommendation around a short quiz
Keep it to 5 to 7 questions:

Height, weight, boot size, and gender or fit preference (these drive sizing)
Riding style they’re drawn to: all-mountain, freestyle/park, or powder/freeride
Where they’ll ride most (resort groomers, park, backcountry someday)
Budget, and whether they plan to buy or rent for the first season
Where they want to be in 1 to 2 years

Core domain logic to encode

Boards: Beginners usually do best with a soft-to-medium flex, a twin or directional-twin shape, and rocker or hybrid camber for forgiveness. Length depends on weight and height, and width matters if boot size is large (to avoid toe drag).
Boots: Fit matters more than any other gear choice. Flex should be soft-to-medium for beginners. Offer lacing options (traditional, quick-pull, BOA) with the tradeoffs of convenience vs. repair and fit.
Bindings: Flex should roughly match the board. Check mounting compatibility (2x4, 4x4, 3D, channel systems). Strap vs. rear-entry vs. step-on systems have different tradeoffs in convenience and response.
Stance: Regular vs. goofy, and a beginner-friendly stance width and angles.

Make the progression path the differentiator
Most beginner guides stop at “buy this.” You can show:

Which items to buy now and which to upgrade later (boots and bindings often last longer than a first board)
A “first board” vs. “next board” roadmap by riding style: park, all-mountain, or powder
A “grow-with-you” mode that avoids gear they’ll outgrow in a season

Be honest about rent vs. buy
Many beginners should rent for the first few days. A “should I buy yet?” checklist builds trust and makes your later recommendations more credible, especially since affiliate revenue creates an incentive to always say “buy.”

Don’t forget the rest of the kit
Helmet, goggles, wrist guards, impact shorts, and layering are things beginners often overlook. They’re also natural affiliate add-ons.

Content beyond gear
Light content makes the app sticky: how to choose a first lesson, regular vs. goofy test, basic terminology, resort etiquette, and common beginner mistakes.

Risks to plan for

Fit is personal. Make it clear that online recommendations are a starting point, and encourage trying boots on in a shop.
Affiliate bias. Disclose partnerships, and consider including non-affiliate options so recommendations don’t feel pay-to-play.
Catalog upkeep. Gear changes yearly, so keep your catalog small (maybe 3 to 5 options per category per riding style) and plan an annual review.
Expertise credibility. Having a snowboard instructor or shop fitter review your logic would add real authority.

MVP suggestion
Start with the quiz plus a results page showing the spec profile and 2 to 3 example products per category, with a short “why this fits you” explanation. Add the progression roadmap as the second release. A simple web app or PWA is enough to test it.

One question that would help me tailor this: is the audience mainly adults trying snowboarding for the first time, or does it include parents buying gear for kids? Kids’ gear has very different sizing and growth considerations, so it affects the quiz design.