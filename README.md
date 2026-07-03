# family-data

Data repo for [Stem & Branch](https://github.com/cjwilduk/echelon9-website/tree/main/stem-and-branch),
a private family tree app. This repo holds only encrypted family bundles and the
public family manifest, nothing else:

- `families.json`: public manifest, slug and display name only, no family data.
- `data.enc`, `data-<slug>.enc`: AES-256-GCM encrypted family bundles (people,
  unions, media, facts). Each one is only readable with that family's passphrase;
  the ciphertext here is not sensitive on its own.

Nothing plaintext ever belongs in this repo. The local sources of truth
(`data.js`, `data-<slug>.js`) live only on the machines that edit them, gitignored,
never pushed anywhere, including here.

Served via GitHub Pages at `https://cjwilduk.github.io/family-data/`. The app in
`echelon9-website` fetches these files cross-origin and writes new versions back
via the GitHub Contents API when someone publishes an edit.

Repo scope, deliberately: a leaked publish token or compromised family device can
at most write encrypted bundles and the manifest here, nothing on the business
site, because this repo holds nothing else.
