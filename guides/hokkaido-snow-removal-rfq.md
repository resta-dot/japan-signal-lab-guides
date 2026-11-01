# How to find Hokkaido snow removal RFQs

For snow-clearing contractors and equipment-rental teams able to serve Japanese sites, a useful procurement feed answers three questions: what service is requested, when is the quotation due, and where are the official requirements? A request for quotation (RFQ) is a request for prices, not an awarded contract.

The [Japan Public Procurement Signals Actor](https://apify.com/japan_signal_lab/japan-buying-intent-signals) can filter selected Forestry Agency notices for Hokkaido snow removal and snow-clearing equipment rental. Start with the [free dated output sample](../samples/buying-intent-2026-10-22.json) and [copyable snow-workflow input](../samples/inputs/procurement-snow-preview.json). No account or Actor execution is needed to inspect those files.

## Decide whether the source fits your business

This workflow covers selected Forestry Agency quotations discovered through the [official Japanese government procurement API](https://www.kkj.go.jp/s/). It is not a nationwide snow-removal tender database, a list of private buyers or a qualification check. The issuer's prefecture can differ from the actual work site. Read the Japanese source and confirm that your business can meet its requirements before preparing a quote.

The Japanese keyword `除雪` refers to snow clearing; `除排雪` also covers removing or hauling snow. These are literal title/subject filters, not translations of detailed specifications. A generic category such as `other` does not mean that a matching snow-service subject is irrelevant.

## Inspect a real notice before running anything

The dated excerpt includes a Rumoi South Forestry Office equipment-rental RFQ, `令和8年度留萌南部森林管理署構内除排雪機械賃貸借単価契約(第1号~第3号)`. It was checked on **22 October 2026 JST**, with response date **6 November 2026**. That is a snapshot, not confirmation that the notice is still open when you read this page.

| Field | What to review |
| --- | --- |
| `expectedPurchase` and `sourceTitle` | The Japanese service/subject; inspect the original specification for machines, hours and quantities |
| `deadline` and `deadlineEvidence` | The response date, not the work-completion date; check the exact closing time at source |
| `sourceUrl` | The [official notice](https://www.rinya.maff.go.jp/hokkaido/apply/publicsale/rumoinanbu/attach/pdf/261021-1.pdf), including eligibility and submission instructions |
| `license`, `attribution`, `retrievedAt` | Source rights, processing disclosure and the age of the excerpt; retain them with an export |

This notice bundles several lots. One Dataset record is one notice/version, not one machine or lot. The English explanation here does not replace the Japanese specification. If the dated example has closed, it remains useful for inspecting the format; do not treat its original `open` label as live availability.

## Try a focused live preview

1. Open the [Actor Input page](https://console.apify.com/actors/e5ioYzQlqwUbTBxLK/input), choose **JSON**, and paste the [snow-workflow input](../samples/inputs/procurement-snow-preview.json) below.
2. Check your available Apify credit and maximum run charge. The unchanged published price is **$0.005 per run + $0.01 per emitted notice**; this input's ten-notice maximum costs at most $0.105 in PPE charges. A zero-match run still costs $0.005, and each repeated preview is billable again.
3. Start the run, then open **Procurement notices (Dataset)**. Read the buyer, Japanese subject, response date and official link. Open **Source coverage and zero-result explanation** to distinguish no matching notice from a source failure or result cap.
4. Add useful results to your own review sheet. Assign a reviewer and a bid/no-bid decision only after checking the original's site, eligibility, specification, time and submission method. The Actor does not send a message or submit a quotation.

```json
{
  "sources": ["forestry-quotes"],
  "lookbackDays": 30,
  "maxResults": 10,
  "onlyChanges": false,
  "keywords": ["除排雪", "除雪"],
  "prefectures": ["北海道"]
}
```

The keywords are OR matches: either can retain a notice. All other conditions still apply, including the 30-day source-date window and exclusion of expired/cancelled or unknown-deadline notices. Current match counts can be zero; the Actor never fills a live preview with archived examples.

## Monitor only after a useful preview

If the feed fits your work, change `onlyChanges` to `true`, use a stable monitor name and keep the same filters. The first completed monitoring run emits current matches, and later runs suppress unchanged versions. Use `eventId` to upsert/deduplicate in your own spreadsheet or integration; interrupted delivery can repeat a version. A run with no new notice still has the start charge.

Saving a Task or setting a schedule is your choice. Reading this guide creates neither. See the [complete Japan RFI and RFQ workflow](find-japan-rfi-rfq-opportunities.md) for the other supported use cases and API defaults.

## Source and feedback

Japan Signal Lab operates the linked paid Actor and processes the excerpts. The issuing agencies do not endorse this guide. See the [source and reuse notes](../SOURCES.md) and retain each row's source/processing attribution. No officials' contact details, bidder lists, private customer data or PDFs are redistributed here.

If the fields do not support your review process, the optional [workflow feedback form](https://github.com/resta-dot/japan-signal-lab-guides/issues/new?template=workflow-feedback.yml) accepts a concrete job or missing-field question. Do not post credentials, customer records or personal contacts. No purchase, review or testimonial is required.
