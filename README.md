# Edgar9

Edgar9 is a business assessment tool by Molho Secreto. It asks a few quick questions and scores the answers using the Edgar9 rules, which come from the original Edgar9 spreadsheet.

**Live site:** https://faustovanin.github.io/edgar9/

## How it works

- **Express route:** the questions depend on the respondent's profile and the business stage:
  - **Idea stage, any profile:** customer, competitors, funding, planning and validation, scored on Market Clarity and Readiness.
  - **Leaders past the idea stage:** 9 questions scored on Entrepreneurial Stance, Market Clarity and Management.
  - **Employees past the idea stage:** the Organization Profile survey, which places the company on a 4-band scale (Traditional, Startup, Collaborative, Hacker).
  - **Customers past the idea stage:** scored on Engagement and Loyalty.
- **Complete route:** the full Edgar9 model (Exponential, Tipping and Coring potentials, with benchmarks). It's in the code but hidden for the first release; set `ENABLE_COMPLETE_ROUTE = true` in `index.html` to turn it back on.
- **Languages:** English and Portuguese.

## Privacy

Nothing is stored on a server. The answers live in the browser while the test is filled in. **Copy Link** encodes the whole assessment in the URL (`?id=…`), so anyone who has the link can see the answers.

## Development

It's a single static page (`index.html`) that loads React, Babel and Tailwind from CDNs, with no build step. To run it locally, open `index.html` in a browser or serve the folder:

```sh
python3 -m http.server 8000
```

The scoring engine is the plain `<script>` block marked `// Edgar9 scoring engine`. Publishing is done by GitHub Pages from the `main` branch.
