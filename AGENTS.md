# Repository guidelines

- This is the public MIT publication and archive repository for **This Week in Crypto**, part of **This Week In Newsletters**, maintained by z08 Studio.
- The private companion `z08-studio/gen-newsletter-crypto` owns collection, research, curation, writing and the sole publication template. Never add a local `templates/` directory.
- Publish every Thursday at `https://thatweekincrypto.substack.com/`. The collection window is Asia/Shanghai `[previous Thursday 00:00, issue Thursday 00:00)`.
- Keep the README focused on readers: banner, short introduction, subscription and suggestions. Maintenance instructions live in `docs/maintenance.md`.
- Use `assets/avatar.png` for the emerald folded C identity and `assets/banner.png` for the README masthead.
- Create empty ignored drafts using `scripts/newsletter.sh new [YYYY-MM-DD]`. Default to the upcoming Thursday in Asia/Shanghai, including today. Explicit valid dates override the default.
- Copy only reviewed Formatted output into drafts. Archive only regular draft files with valid issue filenames and calendar dates after publication is confirmed. Never replace an existing draft or archive.
- Keep credentials, raw candidates, caches, unpublished drafts and their attachments out of Git. Do not copy other projects' secrets, runtime outputs, branding or Git history.
- Run `bash -n scripts/newsletter.sh` and `python3 -B -m unittest discover -s tests -v` after changing maintenance tools. Preserve executable permission.
- Publishing an issue and archiving it require a direct user request. No command publishes automatically.
- Keep tracked documentation and newsletter content in English. Commit directly to `main`; create a PR only if explicitly requested.
