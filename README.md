# js-json-response-normalizer

A JavaScript utility to normalize API responses containing article objects. It filters out unpublished draft articles and simplifies the data structure of published articles into concise summaries.

## Features
- **Filter Articles**: Extract only the articles that are marked as `'published'`.
- **Transform Structure**: Maps the verbose article structure (with nested `author.name` and `stats.views`) into a flat summary object containing `id`, `title`, `authorName`, and `views`.
- **Normalize**: Combines both operations to process a raw JSON API response.

## Functions

### `getPublishedArticles(response)`
Filters an API response to return only articles with `status: 'published'`.

### `toArticleSummary(article)`
Transforms a detailed article object into a simplified summary:
- `id`
- `title`
- `authorName` (extracted from `article.author.name`)
- `views` (extracted from `article.stats.views`)

### `normalizeArticles(response)`
The main helper that takes a full API response, filters the published articles, and maps them to their summary representations.

## How to Run

To run the project, execute the following command:

```bash
node main.js
```

### Sample Output

```javascript
[
  {
    id: 'a1',
    title: 'Learning JavaScript',
    authorName: 'Ava Stone',
    views: 1200
  },
  {
    id: 'a3',
    title: 'Async Basics',
    authorName: 'Mina Patel',
    views: 900
  }
]
2
{
  id: 'a1',
  title: 'Learning JavaScript',
  authorName: 'Ava Stone',
  views: 1200
}
```

Project page url: https://roadmap.sh/projects/js-json-response-normalizer