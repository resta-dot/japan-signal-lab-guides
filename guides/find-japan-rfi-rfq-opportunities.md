# How to find Japanese public-sector RFI and RFQ opportunities

For facilities-maintenance, equipment-service and software vendors researching Japanese public procurement, the first question is not “how many leads?” It is whether a notice asks for your product or service, what stage it represents, and when a response is due.

This guide covers a small source-linked feed: selected Forestry Agency quotation notices and Osaka City's Digital Administration Bureau RFIs. It is not a nationwide tender database, a private-company contact list or a promise of sales.

## Inspect three real examples without an account

Open the [free three-notice RFQ JSON excerpt](../samples/buying-intent-2026-10-13.json). Use GitHub's **Raw / Download raw file** control if you want the JSON file. No Apify account, email signup or Actor execution is needed.

The excerpt was checked on **13 October 2026 JST** and contains selected fields from a local source check, not a customer run. The records' status is a snapshot at retrieval; later deadlines, cancellation or corrections may change the opportunity. Follow each official source link before acting.

| Check | What the first dated example shows | How to use it |
| --- | --- | --- |
| Buyer | Forestry Agency Hokkaido office (`林野庁北海道森林管理局`) | Identify the official issuer, not a private-company prospect |
| Subject | `奥尻地区公務員宿舎修繕工事` — official-housing repair works | Read the Japanese subject and original requirements to assess fit |
| Stage | `request_for_quotation` | A quotation request, not an awarded contract |
| Response date | `2026-10-21` in the source evidence | Check the original notice for exact closing time and submission procedure |
| Provenance | Official Forestry Agency URL, PDL1.0 and processing attribution | Keep these fields with any exported or shared excerpt |

Other generic subjects remain category `other`; the feed does not invent the equipment list or translate detailed specifications. The `confidence` field is extraction-rule evidence, not purchase or win probability.

## Why manual monitoring is awkward

Publication/indexing dates, question deadlines and response deadlines are not interchangeable. Corrected notices can supersede older versions, and government sales or contract results should not be treated as open purchase requests. Separate offices publish Japanese notices with different structures.

The [Japan Public Procurement Signals — RFI & RFQ Actor](https://apify.com/japan_signal_lab/japan-buying-intent-signals) normalizes selected facts and retains their evidence. It does not inspect restricted attachments, determine supplier eligibility or send messages to buyers.

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

The local check on 13 October found six qualifying Forestry Agency RFQs and no discovered Osaka RFI, with both sources responding and no source cap. This is a dated observation, not a guaranteed supply of open opportunities. No historical or fictional record is inserted into a live run.

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
