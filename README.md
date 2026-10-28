**Status: in preparation. Sizes and counts are estimates; folder names are planned. This is not an official publication of any court or of the Government of India.**

# Indian Law Open Data

Indian Law Open Data is a planned collection of Indian law, prepared by AVGAN SERVICES PRIVATE LIMITED (Secunderabad, India). It is planned to be free to use and openly licensed, for the Indian public.

## What it is

The planned collection has four parts:

- The Constitution of India.
- Central and State Acts, with their sections, rules and notifications.
- Judgments of the Supreme Court of India.
- Judgments of the High Courts.

Each legal item is planned to carry its date and its territory, so a reader can see which version applied on a given date.

The compilation, the structure and the data we add are planned to be released under the Creative Commons Attribution 4.0 licence (CC BY 4.0). Statutory text and judgment text are copied exactly as published. They are never rewritten.

## Who it is for

The collection is planned for the Indian public, including:

- Litigants who want to read the text of a provision, or check which version applied to their matter.
- Lawyers and their staff.
- Students of law.
- Researchers studying Indian law or court decisions.
- Journalists checking what a law or a judgment says.
- Legal-technology builders who need a dated, structured base to build on.

## What it will contain

Planned sources, to be confirmed at each publisher before first release:

- India Code (Legislative Department) for the Constitution of India and for Acts.
- The Supreme Court of India and the High Courts (eCourts) for judgments.

Planned content:

- The Constitution of India, by article.
- Central and State Acts, by section, with the rules and notifications that belong to each Act.
- Supreme Court of India judgments and High Court judgments, with case details, judgment date and full text.
- Dates and versions. When a provision is amended, omitted or repealed, the earlier text is planned to be kept, with the dates it applied, and not deleted. A repealed Act stays in the collection, with the date it stopped being in force.

Planned update schedule: Acts weekly; judgments periodically. No release dates are set.

Every record is planned to carry three things, so that it can be checked at the original source:

- The address of the original publisher's page.
- A content hash of the text as copied.
- The date the record was last checked against the publisher.

## Formats and layout

Planned formats:

- Apache Parquet, partitioned by territory and item type.
- JSON Lines.
- CSV lookup files, for example for territory and court names.
- An Amazon Athena tutorial showing how to query the Parquet files with SQL.

The data dictionary, with planned table and column names, is planned at `opendata/docs/dataset.md`. Folder names and file paths are planned and will be fixed before release.

## Licence and attribution

- The compilation, the structure and the added data: Creative Commons Attribution 4.0 International (CC BY 4.0), https://creativecommons.org/licenses/by/4.0/
- The underlying texts remain subject to the terms of their original publishers. Those terms are to be confirmed at each publisher before first release.
- When you reuse the data, credit AVGAN SERVICES PRIVATE LIMITED, link to this repository, and keep the publisher page address that each record carries.

## How to cite

Use this template, and replace DATE with the date you accessed the data, in YYYY-MM-DD form:

```
AVGAN SERVICES PRIVATE LIMITED, "Indian Law Open Data", <file or record name>, <original publisher page address>, accessed DATE, licensed under CC BY 4.0, https://gshilp.com
```

When you quote legal text, also cite the original publisher's version.

## Contact

AVGAN SERVICES PRIVATE LIMITED
Secunderabad, India
Website: https://gshilp.com
E-mail: gandhishilp@gmail.com

## Disclaimer

- This collection is not legal advice. Using it does not create a lawyer-client relationship.
- The original publisher's version governs. If this data differs from the publisher's text, the publisher's text is the authority.
- Users must check the original publisher's page before relying on any text, date or version.
- The date last checked on each record shows when it was last compared with the publisher. The record may be older than the publisher's current text.
