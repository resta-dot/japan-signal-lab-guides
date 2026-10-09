# Japan Signal Lab: Japanese supplier and alcohol-market research

Practical guides and small, dated samples for teams working with Japanese companies. Inspect the data before deciding whether an automated workflow is useful.

| Your job | Start here | Inspect without running an Actor |
| --- | --- | --- |
| Keep an existing Japanese supplier or CRM list up to date | [Monitor Japanese suppliers for closures and address changes](guides/monitor-japanese-suppliers.md) | [Company-by-company check CSV](samples/supplier-check-2026-09-20.csv) and [coverage JSON](samples/supplier-check-2026-09-20.json) |
| Research potential Japanese alcohol wholesale or ecommerce partners | [Find alcohol wholesalers and ecommerce operators in Japan](guides/find-japan-alcohol-partners.md) | [Three-record partner-research CSV](samples/liquor-partner-research-2026-09-20.csv) |

**These are historical examples, not live company-status certificates, verified buyers or customer results.** Each guide explains the dates, scope, source and limitations. Samples were checked on 2026-09-20. Download a CSV using GitHub's **Raw / Download raw file** control. Import corporate numbers as **Text**, not numbers, in Excel or your CRM.

## Get a fresh result for your own workflow

- [Japan Supplier & KYB Change Monitor on Apify](https://apify.com/japan_signal_lab/japan-signal-lab): exact corporate-number watchlist monitoring, with a separate company-by-company check report.
- [Japan Liquor License Leads & Signals on Apify](https://apify.com/japan_signal_lab/japan-liquor-license-signals): official monthly liquor-license publications, with a small first-run preview.

Japan Signal Lab publishes these guides and operates the linked **paid** Actors. Static samples are free to inspect; running an Actor uses its published pay-per-event pricing and available Apify credits. No account is needed to read these guides. There is no email signup, contact enrichment or advertising tracker.

## Try the output without preparing your own input

- [Supplier historical demo — one official event, expected PPE $0.0152](https://console.apify.com/actors/0NQVu328uYLMIEeJ3/input): keep the sample number and click **Start**. For your own list, open **Customize**, clear the historical end date and choose the audit period.
- [Liquor historical demo — ten records, expected PPE $0.12](https://console.apify.com/actors/oADiu8kyT9Zo1PP7X/input): keep **Hokkaido / 10 results** and click **Start**. For current research, open **Customize** and clear the July 2026 month.

Both demo sources were rechecked on 2026-10-10. They are historical examples, not live status certificates or buyer lists. If you previously used an Actor, **Restore example input** replaces your saved form with the demo; existing API calls and saved tasks are not migrated.

**Is trying again free?** The static files above can be inspected repeatedly without running an Actor or creating an account. Each Actor run, including a repeated demo, uses the published PPE pricing again. Available Apify account credits may cover a run, but this is not an unlimited free trial. Check your available credit before starting; reopening a saved result does not rerun it.

## 日本語での用途

- **取引先台帳の更新確認**：既存の法人番号一覧と国税庁の日次差分を照合し、変更が見つかった企業・確認範囲が不足した企業を区別します。「変更なし」は現在の法的状態や健全性の保証ではありません。
- **酒類事業者の提携候補調査**：卸売・輸出入・通信販売の免許区分と変更内容を出典付きで確認します。新設企業一覧、購入意欲や提携希望の確認済みリストではありません。

## Questions or useful missing fields?

Use this repository's [workflow feedback form](https://github.com/resta-dot/japan-signal-lab-guides/issues/new?template=workflow-feedback.yml). Describe the job you are trying to do and which sample field is missing. Do not post API tokens, private watchlists, customer information or personal contact details. A public issue is optional; no review or testimonial is requested.

## Source and reuse

Samples contain selected corporate public records, not personal contact lists. They are processed by Japan Signal Lab, not endorsed or produced by the National Tax Agency. See [source and reuse notes](SOURCES.md). Actor source repositories remain private; this repository contains only publication-ready guides and examples.
