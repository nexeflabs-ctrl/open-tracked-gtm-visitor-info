# Open Tracked Visitor Info

_Server variable template for Google Tag Manager (server container)._

Returns one thing about the visitor of the event: country, region, city or postal code (from the visitor-location headers Cloudflare adds), operating system, browser, mobile or not (from the user agent), or an anonymous visitor ID. If the event already carries the value, that one wins. Use it in an **Augment event** transformation to give Meta, TikTok and Google Ads the details they use to match visitors.

## How to use

1. Add the variable to your server container and choose **What to return**.
2. Optionally set the event data key whose own value should win (for example `user_data.address.country`).
3. Use the variable in an **Augment event** transformation or directly in a tag.

## Fields

| Field | Name | What it does |
|---|---|---|
| What to return | `info` | Country, region, city and postal code are read from Cloudflare's visitor-location headers, so they are only there when your tagging domain goes through Cloudflare (city, region and postal code also need its Add visitor location headers setting). |
| Use the event's own value first (optional) | `eventDataKey` | An event data key such as user_data.address.country. When the event has it, that value is returned. |

## Privacy

- The variable only reads headers of the incoming request and the event. It does not send anything anywhere.
- The visitor ID is a hash of the visitor's address, browser and your tagging host; it changes when one of them changes.

## Permissions

- **Reads event data**: Reads the optional event value.
- **Reads HTTP request**: Reads the visitor-location headers and the user agent.

## Notes

No account is needed. Country, region, city and postal code are only there when your tagging domain is served through Cloudflare (or another CDN that sends the same headers).

## About Open Tracked

[Open Tracked](https://opentracked.io) is a first-party tracking service: a tagging server on your own domain, an analytics pixel and a CRM. Documentation: https://docs.opentracked.io/google-tag-manager

## License

Apache License 2.0, see [LICENSE](LICENSE).
