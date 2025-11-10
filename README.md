## ticket-fake-api — read-only JSON API for tickets

This repository hosts a small fake JSON API (powered by my-json-server) that serves a collection of ticket objects.

### Base endpoints

- Base URL for all tickets collection:

  `https://my-json-server.typicode.com/j-handlechner/ticket-fake-api/tickets`

- Single ticket (by id):

  `https://my-json-server.typicode.com/j-handlechner/ticket-fake-api/tickets/<id>`

### Querying and pagination examples

- Filter by field (example: price equals 10):

  `https://my-json-server.typicode.com/j-handlechner/ticket-fake-api/tickets?price=10`

- Pagination / limits:

  `https://my-json-server.typicode.com/j-handlechner/ticket-fake-api/tickets?_page=2&_limit=10`

### Images

The `img` attribute in the JSON refers to the **Unsplash ID** of the images. To build the URLs, use this schema:

- `https://images.unsplash.com/photo-<image id from json api>`
- for example: `https://images.unsplash.com/photo-1531436040007-7216019112d7`

### JSON structure (db.json)

The API serves a top-level object with a `tickets` array. Each ticket object contains the following fields:

- id (number) — unique identifier
- title (string) — short title of the ticket
- shortDescription (string) — brief summary
- detailledDescription (string) — longer description (note the spelling in the data)
- price (number) — regular price
- priceReduced (number, optional) — reduced price when available
- isFeatured (boolean, optional) — flag for featured tickets
- img (string, optional) — image filename or path

Example ticket object:

```json
{
  "id": 1,
  "title": "Day Ski Pass",
  "shortDescription": "Full-day access to all ski lifts.",
  "detailledDescription": "Enjoy unlimited skiing across the entire resort for one full day.",
  "price": 59,
  "priceReduced": 49,
  "isFeatured": true,
  "img": "ticket-1.png"
}
```

### Notes

- This is a read-only fake API (my-json-server) — POST/PUT/PATCH/DELETE won't persist changes.
- Field names mirror `db.json` in this repo (see `db.json`).
