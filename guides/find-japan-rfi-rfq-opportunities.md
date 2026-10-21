# How to find Japanese public-sector RFI and RFQ opportunities

For facilities-maintenance, equipment-service and software vendors researching Japanese public procurement, the first question is not “how many leads?” It is whether a notice asks for your product or service, what stage it represents, and when a response is due.

This guide covers a small source-linked feed: selected Forestry Agency quotation notices and Osaka City's Digital Administration Bureau RFIs. It is not a nationwide tender database, a private-company contact list or a promise of sales.

## Inspect three real examples without an account

Open the [free three-notice RFQ JSON excerpt](../samples/buying-intent-2026-10-22.json). Use GitHub's **Raw / Download raw file** control if you want the JSON file. No Apify account, email signup or Actor execution is needed.

The excerpt was checked on **22 October 2026 JST** and contains selected fields from a local source check, not a customer run. All three response dates were in the future on that date. The dates were also cross-checked against the public official notices. The records' status is a snapshot at retrieval; later deadlines, cancellation or corrections may change the opportunity. Follow each official source link before acting.

| Check | What the first dated example shows | How to use it |
| --- | --- | --- |
| Buyer | Forestry Agency Hokkaido office (`林野庁北海道森林管理局`) | Identify the official issuer, not a private-company prospect |
| Subject | `令和8年度網走西部森林管理署西紋別支署宿舎浴室修繕業務` — staff-housing bathroom repairs | Read the Japanese subject and original requirements to assess fit |
| Stage | `request_for_quotation` | A quotation request, not an awarded contract |
| Response date | `2026-11-06` in the source evidence | Check the original notice for exact closing time and submission procedure, not just the date |
| Provenance | Official Forestry Agency URL, PDL1.0 and processing attribution | Keep these fields with any exported or shared excerpt |

Other generic subjects remain category `other`; the feed does not invent the equipment list or translate detailed specifications. The `confidence` field is extraction-rule evidence, not purchase or win probability.

The [13 October excerpt](../samples/buying-intent-2026-10-13.json) is retained as an **archive**: its three response dates were 20–21 October and have passed. Do not treat its original `open` snapshot labels as current availability. No historical record is rewritten to look new.

## Why manual monitoring is awkward

Publication/indexing dates, question deadlines and response deadlines are not interchangeable. Corrected notices can supersede older versions, and government sales or contract results should not be treated as open purchase requests. Separate offices publish Japanese notices with different structures.

The [Japan Public Procurement Signals — RFI & RFQ Actor](https://apify.com/japan_signal_lab/japan-buying-intent-signals) normalizes selected facts and retains their evidence. It does not inspect restricted attachments, determine supplier eligibility or send messages to buyers.

## Three practical workflows with copyable inputs

These workflows are for teams able to deliver the relevant services in Japan. The short English subject descriptions below are guide explanations, **not Actor-generated translations or specifications**. The actual notice titles and filter keywords are Japanese. Procurement qualifications still apply; none of these examples establishes that your business is eligible or will win a contract.

### 1. Facilities maintenance: a bathroom-repair bid/no-bid queue

**Who:** a local maintenance contractor's estimating coordinator, or a procurement researcher supporting that team.

**Job:** find a relevant quotation request, open the original specification and decide whether to allocate time to a quote. The sample is the West Monbetsu staff-housing bathroom repair RFQ, with response date **6 November 2026**, as checked on 22 October.

Use the [bathroom-repair preview input](../samples/inputs/procurement-facilities-preview.json). It selects Forestry notices in `北海道` and the literal keyword `浴室修繕`. It matched one qualifying notice in the dated local check. After running, open its `sourceUrl`, verify the work scope, eligibility, deadline time and submission method, then record your own review decision in a spreadsheet or CRM. The Actor does not prepare or submit a quotation.

### 2. Vehicle servicing: route a matching notice to the right workshop

**Who:** a vehicle inspection/maintenance provider with an appropriate Japanese service operation.

**Job:** identify an official-vehicle inspection RFQ before reviewing the service locations and specification. The sample is the Hidaka North official-vehicle inspection notice, with response date **9 November 2026**, as checked on 22 October.

Use the [vehicle-service preview input](../samples/inputs/procurement-vehicle-preview.json), which filters `北海道` plus `自動車点検`. It matched one notice in the dated local check. Route the source link, Japanese subject and response date to a human reviewer. Check the original's lots and vehicle/service requirements; an issuer's prefecture is not a guaranteed delivery location or proof of your service capability.

### 3. Snow equipment rental: compare lots before scheduling a review

**Who:** an equipment-rental or snow-clearing operator already able to serve the source locations.

**Job:** shortlist rental requests, then inspect the official lots, equipment requirements and quantities. The sample is the Rumoi South snow-clearing equipment rental notice, with response date **6 November 2026**, as checked on 22 October.

Use the [snow-equipment preview input](../samples/inputs/procurement-snow-preview.json), which matches `除排雪` **or** `除雪` in `北海道`. It matched three notices in the dated local check; the free excerpt includes one of them. One notice can bundle several lots: the Dataset charges/counts notices, not individual machines or lots. Do not infer a confirmed rental or awarded contract from an RFQ.

### Load a preset without changing the first-run defaults

Download one input JSON above, open the Actor's Input page, switch to **JSON**, and paste the file. The presets all use a maximum of ten results and `onlyChanges: false`; they do not change your existing saved Tasks or create a schedule. Each new preview is billable. For a quick unfiltered look instead, leave the normal ten-result form unchanged.

The sample's later-deadline notices need not appear in the **first ten** unfiltered results. Use the matching preset to focus the feed. Preset match counts above describe only the 22 October source check; future runs can have fewer or no results. Do not raise the minimum evidence score merely because a useful literal subject has category `other`.

If the preview fits, switch `onlyChanges` to `true`, choose a stable monitor name and keep the same filters for recurring monitoring. Your own review sheet can track reviewer, next action and bid/no-bid status; those are **your workflow fields**, not extra fields supplied by this Actor. No message, buyer contact or quotation is sent automatically.

## Try up to ten live notices

1. Open the [Actor's Input page](https://console.apify.com/actors/e5ioYzQlqwUbTBxLK/input).
2. Keep **Maximum results — keep 10 for the live preview**. The supported sources and other filters are under **Customize**; you do not need your own keywords or company list for the first run.
3. Check your available Apify credit. Published PPE is **$0.005 per run + $0.01 per emitted notice**: ten costs $0.105, six $0.065, zero $0.005. You may set a maximum run charge; $0.11 covers ten at these prices.
4. Click **Start**, then open **Procurement notices (Dataset)**. Compare buyer, Japanese subject, stage, deadline and source URL; export JSON or CSV if useful.
5. Open **Source coverage and zero-result explanation** to check source health, filtering and result/budget caps. A zero-result or partial check is not evidence that all of Japan has no opportunities.

The live preview uses:

```json
{
  "sources": ["forestry-quotes", "osaka-rfi"],
  "lookbackDays": 30,
  "maxResults": 10,
  "onlyChanges": false
}
```

The local 30-day source check on **22 October 2026** found 17 qualifying Forestry Agency RFQs and no discovered Osaka RFI, with both sources responding and no source cap. The normal Store preview returns at most ten of these, ordered by deadline. This is a dated observation, not a guaranteed supply of open opportunities. No historical or fictional record is inserted into a live run.

## RFQ is not RFI, and neither guarantees a sale

- **RFQ / quotation request:** an official request for prices for goods or services. Review qualifications, scope and submission instructions at source.
- **RFI / information request:** early research into available products or services, not a committed purchase, awarded budget or order. The supported Osaka source may have no current RFI.

If you sell software, do not treat a facilities RFQ as software intent. Select the Osaka source or relevant literal keywords for focused research, accepting that a narrow feed can have no matches. Full Japanese prefecture names filter source-reported location; that is not always the work/delivery site.

## Move a useful preview into recurring monitoring

After verifying that the supported feed fits your work, enable **Only new or changed signals** under **Recurring monitoring** and keep the same monitor name and filters. The first completed monitoring run emits current matches; later completed runs suppress unchanged versions. Save a Task and set your own schedule if you want recurring checks; none is created by reading this guide.

Use `eventId` to upsert/deduplicate downstream. Interrupted delivery can repeat an event. Changes in filters use separate history, and changing the monitor name starts fresh. API calls with omitted options still default to 50 results and change monitoring; existing integrations are not migrated.

## Can I try it repeatedly for free?

The static JSON and guide are free to view repeatedly. **Each live preview is billable again**, including unchanged records. Available account credits may cover it, but this is not unlimited free usage. Reopening an existing Dataset does not rerun the Actor. Even a monitoring run with no new notices incurs the $0.005 start event.

## Official sources and feedback

The feed uses the [official 官公需 API](https://www.kkj.go.jp/s/) as a discovery channel for reviewed Forestry Agency procurement paths, and the [Osaka City Digital Administration Bureau index](https://www.city.osaka.lg.jp/sangyo/category/3047-9-5-1-0-0-0-0-0-0.html) for explicitly licensed public RFI HTML. It does not license arbitrary API-linked publishers or fetch application/NDA materials. See [source and reuse notes](../SOURCES.md) and retain each row's source, license and processing attribution.

Japan Signal Lab operates the linked paid Actor. The guide and excerpts are processed by Japan Signal Lab, not official government advice or endorsement. No officials' contact details, logos, personal addresses or private customer records are redistributed.

If a field is missing for your workflow, use the optional [public workflow feedback form](https://github.com/resta-dot/japan-signal-lab-guides/issues/new?template=workflow-feedback.yml). Do not include credentials, private customer data or personal contacts. No review, purchase or testimonial is required.
