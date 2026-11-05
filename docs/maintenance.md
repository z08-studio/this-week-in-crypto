# Maintenance

This public MIT repository owns publication assets, empty local draft tools and the reviewed archive for **This Week in Crypto**. The private companion [gen-newsletter-crypto](https://github.com/z08-studio/gen-newsletter-crypto) owns collection, research, editorial selection, verified writing, descriptions and the sole content template at `output/templates/formatted_template.md`.

## Weekly workflow

Publish manually every Thursday at [This Week in Crypto on Substack](https://thatweekincrypto.substack.com/). The generator covers Asia/Shanghai `[previous Thursday 00:00, issue Thursday 00:00)`, so the current Thursday starts the next collection window.

1. Run `pnpm newsletter` in the generator, using the intended Thursday issue date.
2. Review its source coverage, evidence, duplicate events, attribution and reader draft. Correct the draft and review `output/final/description.txt` before publication.
3. Create an empty local draft using `./scripts/newsletter.sh new [YYYY-MM-DD]`, copy only the reviewed Formatted output into it and make final edits.
4. Publish manually in Substack, verify the final draft against the published article, then archive it and update the README's latest-issue links.

Generating content, creating a draft and creating a repository do not publish an issue. The archive is reserved for reviewed, published editions. Unpublished drafts and attachments remain ignored.

## Drafts and archives

Use Bash and the system `date` command on macOS or Linux:

```sh
./scripts/newsletter.sh new
./scripts/newsletter.sh new 2026-11-05
```

The default is the upcoming Thursday in Asia/Shanghai, including today on Thursday. An explicit valid calendar date overrides the default so a delayed edition can retain its actual publication date. With no prior issues, the example creates the empty file `drafts/2026-11-05-issue-01.md`. Numbering continues across regular drafts and archives.

After publication is confirmed:

```sh
./scripts/newsletter.sh archive 2026-11-05-issue-01.md
```

Only regular files directly in `drafts/`, with valid `YYYY-MM-DD-issue-NN.md` filenames and calendar dates, are archive candidates. Symbolic links, directories and notes are excluded. Existing drafts and archives are protected from replacement. Omit the filename only when exactly one valid regular draft exists.

## Assets

- `assets/avatar.png`: native emerald folded C master.
- `assets/banner.png`: matching editorial README masthead.
- [Branding provenance and prompts](branding.md).

Keep the content template in the generator. Do not create a publication-local `templates/` directory or commit collected source material, provider records, credentials or runtime caches.

## Checks

```sh
bash -n scripts/newsletter.sh
python3 -B -m unittest discover -s tests -v
```

Tests use temporary fixtures and never alter real editions. CI runs the same workflow checks on macOS and Linux.

## Rights

Original project material is available under the [MIT license](../LICENSE). Linked third-party material retains its own ownership. Write original editorial introductions and preserve source links.
