# How to find Japanese alcohol wholesalers and ecommerce operators for partner research

Overseas alcohol brands and distributors entering Japan need to identify businesses worth investigating as potential import, wholesale or online-sales partners. Official liquor-license publications can help establish **which license category and event were published for a business**. They cannot tell you whether that business wants your product or is seeking partners.

This guide turns monthly National Tax Agency publications into a source-linked research table. It is useful for Japan market entry and alcohol ecommerce research, not automated outreach or a verified buyer list.

## Start with a finished research table

[Inspect or download the three-record CSV](../samples/liquor-partner-research-2026-09-20.csv). Use GitHub's **Raw / Download raw file** control, and import the corporate-number column as **Text** in Excel.

These are corporate records from **Hokkaido's July 2026 publication**, published 2026-08-31 and rechecked 2026-09-20. Street addresses and contact details are deliberately omitted from this public sample. The published business-name text is retained, including premises labels and source formatting.

| Corporate number | Published category | Official processing event | Research question |
| --- | --- | --- | --- |
| 4011001009265 | Wholesale/retail | Incorporation-related license processing | Does this location and license category fit the channel being researched? |
| 3430001026519 | Online sales | Relocation | Is this ecommerce operator relevant to the intended geography and product category? |
| 8430001089379 | Import/export wholesale | Relaxation of license conditions | Which conditions changed, and is the official scope relevant to an import/export partnership? |

The sample is deliberately small. It is not a ranking, endorsement, contact list or a claim that these companies are newly established. Read the [original NTA PDF](https://www.nta.go.jp/about/organization/sapporo/sake/menkyo/hambai/data/r08/07/pdf/sapporo.pdf) before making an internal shortlist.

## Build your own shortlist

1. **Pick one channel.** For distributor research use `wholesale_license` and `import_export_license`. For alcohol ecommerce operator research use `online_sales_license`. These labels filter published facts, not buying intent.
2. **Pick relevant prefectures.** A small output cap stops collection early. It is not a complete survey of every selected prefecture, and source discovery order decides which publication is processed first.
3. **Inspect a small result first.** [Japan Liquor License Leads & Signals](https://apify.com/japan_signal_lab/japan-liquor-license-signals) has a prefilled preview of up to 10 records. On 2026-09-20 it returned 10 records from one parsed PDF with 49 source rows and no failed publications. Different dates or filters can produce fewer records, including none.
4. **Keep the original evidence.** Export the corporate number when printed, published business name, prefecture, license category, processing category, effective date, publication date and source link. Missing corporate numbers must remain missing; do not infer them from a similar name.
5. **Add your assessment separately.** Record source checked, geographic fit, channel fit and your own decision. Leave “partnership interest” unknown unless you have separate legitimate evidence. Do not overwrite source facts with assumptions.

## Why “new liquor businesses” needs careful interpretation

A monthly list includes more than newly granted licenses: it can include relocations, incorporation-related processing and changed conditions for established operators. A new record in an export is therefore not necessarily a new business, a pre-opening opportunity or a new purchasing need.

The **effective date**, **publication date** and **date you downloaded the data** answer different questions. Preserve all three. Running a monthly source every day does not make the underlying facts newer. Compare the corporate number, location, event, effective date and source PDF with your previous export before counting a record again.

## Cost of the first check

At existing PPE prices, one successfully parsed PDF plus ten emitted events costs **$0.12** ($0.02 + 10 × $0.01). Three PDFs plus ten events would be $0.16. A successfully parsed PDF with no matching results still incurs its scan fee. Read [current pricing](https://apify.com/japan_signal_lab/japan-liquor-license-signals/pricing) and check your available credit before starting.

The static CSV here is free to inspect and requires no Apify account. Japan Signal Lab publishes this guide and operates the linked paid Actor.

## Official source and responsible use

Source: [NTA liquor-sales-license publication index](https://www.nta.go.jp/taxes/sake/menkyo/shinki/hambai/03.htm), with links to regional monthly publications. Processed by Japan Signal Lab with source and processing disclosure under the [NTA reuse terms](https://www.nta.go.jp/chuijiko/copy.htm). This is not an NTA product.

Some broader publications include sole proprietors; the public sample here contains only incorporated businesses. The Actor does not provide email, phone or personal-contact enrichment. Official license facts do not establish present trading status, commercial suitability, compliance with every rule or willingness to form a partnership.

**Next:** [inspect the sample CSV](../samples/liquor-partner-research-2026-09-20.csv), then [open the Actor](https://apify.com/japan_signal_lab/japan-liquor-license-signals) if this evidence supports your research process.
