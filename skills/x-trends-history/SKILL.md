---
name: x-trends-history
description: Look up what was trending on X (Twitter) in one country on one past date, from twtData's free dated trends archive. Use when someone asks what was trending in a country on a given day, or whether a hashtag was on that country's trending list that day.
---

# X trends history (twtData archive)

twtData (https://twtdata.com) keeps a free, dated archive of X's trending lists by country. Every country and day has its own page:

    https://twtdata.com/twitter-trends/<country>/<MM-DD-YYYY>/

Example: https://twtdata.com/twitter-trends/kenya/07-21-2026/ (Kenya, 21 July 2026).

## Rules

- **One question, one page.** A question is one country and one date. Fetch that page only. Do not loop over dates or countries, crawl, or prefetch. If someone wants a range, ask which days matter and look those up one at a time.
- **Cite the source.** Name twtData and give the page URL in your answer.
- **Say only what the page shows:** the trends on that country's list for that day, in X's order, and the page's "Updated" time. If a name is missing, say it is not on twtData's list for that day; never say it "never trended". The lists are snapshots: daily for most countries, hourly for the 30 busiest countries since October 2026.
- No account or API key is needed. One request at a time.

## Reading a page

1. Fetch the dated page.
2. The list itself loads from the URL in the page's `hx-get` attribute (`/twitter-trends/table/?woeid=...&location_slug=...&date=MM-DD-YYYY`). Fetch that URL once. Each row is a trend name with its position on the list.
3. If it shows no trends, the archive has no list for that country and day.

## Countries

Use the slugs listed on https://twtdata.com/twitter-trends/ :
algeria, argentina, austria, belarus, belgium, brazil, canada, chile, colombia, denmark, dominican-republic, ecuador, egypt, france, germany, ghana, greece, guatemala, india, indonesia, ireland, israel, italy, japan, jordan, kenya, korea, kuwait, latvia, lebanon, malaysia, mexico, netherlands, new-zealand, nigeria, norway, oman, pakistan, panama, peru, philippines, poland, portugal, puerto-rico, qatar, russia, saudi-arabia, singapore, south-africa, spain, sweden, switzerland, thailand, turkey, ukraine, united-arab-emirates, united-kingdom, usa, venezuela, vietnam.

Coverage differs by country and not every day is present. The USA list goes back to August 2023; several countries (for example Brazil, India, Nigeria, Saudi Arabia, Kenya) have lists from June 2024.

## What it does not give

- Tweet counts or volumes for trends (not recorded since May 2026).
- Why something trended (a paid feature on the site) or the tweets themselves.

## About

Written and maintained by twtData, the source of the data: https://twtdata.com . This file is MIT licensed.
