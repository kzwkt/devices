# devices

Electronics I have owned in this life. A Jekyll site for GitHub Pages: every file in `_devices/` is listed automatically, sorted by purchase date.

## Add a device

1. Copy `_templates/device.md` to `_devices/<short-name>.md`.
2. Fill the front matter and the headings (Overview, Specs, How long it lasted, Experience, Pros and cons, Verdict, Links).
3. Put photos in `img/` and list their file names under `images:`. Each photo keeps its own shape in the strip, and clicking one opens it full-size, with < > to move through the rest.
4. Commit and push. Pages rebuilds in about a minute. You can also edit any device page straight from the site via "Edit on GitHub".

Markdown gotcha: kramdown only recognizes a table when a blank line comes before it. `## Specs` glued to `| Part | Detail |` renders as a paragraph of pipes, with `|---|---|` turned into em dashes.

Front matter gotcha: a device file must open with `---` and close with `---`. If the opening line is missing, Jekyll sees no metadata, silently skips the file and the device just vanishes from the site with no build error. The site builds fine either way, so count the devices on the index after adding one.

Front matter:

| Field | Needed | Meaning |
|---|---|---|
| title | yes | Name shown everywhere |
| bought | no | YYYY-MM-DD. Without it the device sits under "Date unknown" at the bottom |
| bought_precision | no | `day` (default), `month` or `year`, for fuzzy dates |
| type | no | Phone, Laptop, ... becomes a filter button |
| status | no | In use, Dead, Sold ... |
| price | no | Quote it: `"Rs 5,600"` |
| warranty_until | no | Date |
| ended | no | Date it died, was sold or retired. The page then shows how long it lasted, otherwise how long you have owned it |
| images | no | List of photo file names inside `img/`, e.g. `- uwell-caliburn-g3.jpg`. Shows as a photo strip next to the details, and the first one becomes the card thumbnail. Full paths (`/img/x.jpg`) and https URLs also work. Missing files are skipped, and with no photos the page is just text |
| media | no | `left` (default) or `right`: which side the photos sit on |

## Publish

Settings > Pages > Deploy from a branch > `main` / root. `baseurl` in `_config.yml` must match the repo name.

## Preview locally

    bundle install
    bundle exec jekyll serve

Open http://localhost:4000/devices/
