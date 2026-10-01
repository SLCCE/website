# Publishing news

The News section at `/news/` is built by Jekyll, which GitHub Pages runs on every push to `main`. Each post is one Markdown file in `_posts/`. The header, footer, styling, listing pages, sitemap, and RSS feed are all generated for you.

## Add a post

1. Choose a template from this folder:

   | Type | Template | Use it for |
   |---|---|---|
   | Press release | `press-release.md` | Formal statements for media: partnerships, launches, milestones |
   | Announcement | `announcement.md` | Something people can act on: events, registrations, openings |
   | General update | `update.md` | Short, informal notes on what a chapter or the org has been doing |
   | Story | `story.md` | Longer narrative features about students, volunteers, and classrooms |

2. Copy it to `_posts/YYYY-MM-DD-short-title.md`, for example `_posts/2026-11-03-msen-fall-workshop.md`.
   - The date in the filename is the publish date shown on the site.
   - The rest of the filename becomes the URL: `/news/2026/msen-fall-workshop/`.
   - Use lowercase letters, numbers, and hyphens only.
3. Fill in the front matter (the block between the `---` lines) and replace the placeholder body text. Delete any optional fields you don't use.
4. Put images in `images/news/` and reference them from the site root, for example `/images/news/msen-fall-1.jpg`. Keep each image under about 500 KB.
5. Open a pull request. Once it merges into `main`, the post goes live within a few minutes.

To unpublish a post, delete its file, or add `published: false` to its front matter.

## Authors

Regular authors are defined once in `_data/authors.yml`:

```yaml
jane-doe:
  name: Jane Doe
  role: Outreach Chair, SLCCE at NC State
  image: /images/jane_headshot.jpeg   # square photo, or an SVG icon
```

Then set `author: jane-doe` in a post. Changing the entry updates every post by that author.

## Writing Markdown

```markdown
## Subheading
**bold**, *italic*, [link text](https://example.com)

- bullet list item

> "A pull quote."
>
> — Name, Title

![Image description](/images/news/photo.jpg)
```

## Front-matter reference

| Field | Types | Notes |
|---|---|---|
| `layout` | all | **Required.** One of `press-release`, `announcement`, `update`, `story`. This field sets the post's type. |
| `title` | all | **Required.** Headline. |
| `description` | all | Recommended. 1–2 sentence summary used on cards, in search results, and in social previews. If omitted, the first paragraph is used instead. |
| `subtitle` | all | Optional line under the headline. |
| `image`, `image_alt` | all | Card and social preview image. On stories, it also appears as the large top image. |
| `author` | all | An author id from `_data/authors.yml` (e.g. `slcce`), which supplies the name, role, and icon. A plain name also works. Shown in the byline. |
| `author_role`, `author_image` | all | Only for plain-name authors who aren't in `_data/authors.yml`. |
| `dateline` | press release | City and state, e.g. `RALEIGH, N.C.` |
| `media_contact` | press release | `name`, `title`, `email`, `phone` (each optional). |
| `event_date`, `location`, `cta_text`, `cta_url` | announcement | Shown in a highlighted details box with a button. |
| `chapter` | update | Label shown above the text, e.g. `SLCCE at NC State`. |
| `image_caption`, `gallery` | story | Caption for the top image, and a list of `{src, alt}` photos shown at the end. |

## Previewing locally (optional)

Requires Ruby. From the repo root:

```bash
bundle install
bundle exec jekyll serve
```

Then open http://localhost:4000/news/.
