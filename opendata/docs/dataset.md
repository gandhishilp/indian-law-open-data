# Indian Law Open Data

**Status: in preparation.** Sizes and counts below are estimates, marked as such. Folder names are planned and will be fixed before the first release. This is not an official publication of any court or of the Government of India.

### Summary

This dataset contains Indian law for the public: the Constitution of India, Central and State Acts with their sections, rules and notifications, and the judgments of the Supreme Court of India and the High Courts. Judgments are published by the courts (Supreme Court of India, eCourts). Acts and the Constitution are published by India Code (Legislative Department). Every record carries the address of the original publisher's page, a content hash and the date it was last checked. Our compilation, structure and added data are licensed CC BY 4.0. The original publisher's version governs; this is not legal advice.

For bulk access, use the tar archives and Parquet files. Individual PDF and JSON objects are also exposed, but downloading many of them creates many S3 requests.

## Data

- Constitution of India, by article; Central and State Acts, by section, with rules and notifications, each with `valid_from` / `valid_to` and territory, so a reader can see which version applied on a given date. Repealed and omitted items are kept with the date they stopped applying.
- Supreme Court of India judgments, English and regional languages.
- High Court judgments and orders, 25 High Courts.
- Estimated total: about 1.4 TB (judgments about 1.3 TB; Acts and the Constitution about 2-5 GB as text and Parquet, about 20-40 GB with source PDFs). ESTIMATE, to be replaced by the measured size.
- Planned growth: about 150-250 GB per year, mostly High Court orders. ESTIMATE.

#### Update cadence (planned)

- Judgments: Supreme Court twice a month; High Courts daily.
- Acts and the Constitution: weekly.

### Structure of the data in the bucket (planned)

```
s3://<bucket-name>/
├── constitution/
│   └── parquet/ , pdf/
├── acts/
│   ├── parquet/territory=<India|State>/item_type=<act|section|rule|notification>/
│   └── pdf/territory=<...>/
├── judgments/
│   ├── supreme_court/
│   │   ├── data/tar/year=YYYY/{english,regional}/*.tar + *.index.json
│   │   └── metadata/{json,tar,parquet}/year=YYYY/
│   └── high_court/
│       ├── data/tar/year=YYYY/court=<code>/bench=<name>/<part>.tar + data.index.json
│       └── metadata/{json,tar,parquet}/year=YYYY/court=<code>/bench=<name>/
└── lookups/   (territory, item type, court and bench codes as CSV)
```

Index files (JSON) list the contents of each tar archive, so a user can see what is inside without downloading it.

### Working with the data (planned)

- Acts and the Constitution: Parquet tables `works`, `provisions`, `rules_and_notifications`, `versions`; each row has `publisher_url`, `content_hash`, `last_checked_date`, `valid_from`, `valid_to`, `territory`.
- Judgments: structured metadata in Parquet (case number, judgment date, bench, parties) next to the PDFs. Note: the `year=` folder is not always the judgment date; use the date in the metadata.
- Access without an AWS account: `aws s3 ls s3://<bucket-name>/ --no-sign-request`
- A tutorial for downloading, extracting and querying the metadata with Amazon Athena will be in `opendata/tutorials/`.

### Licence and citation

- CC BY 4.0 for our compilation, structure and added data: https://creativecommons.org/licenses/by/4.0/
- Cite as: AVGAN SERVICES PRIVATE LIMITED, "Indian Law Open Data", accessed DATE, https://gshilp.com
