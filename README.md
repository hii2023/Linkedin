# Signal Frame

Add a status ring to your LinkedIn profile photo so people know what you are open to.

## Features

- 29 signals in five groups: Career, Career Break, Business, Business Needs, Community
- Three frame styles: Arc (LinkedIn side by default, bottom or top), Full ring, Badge
- Custom text, optional hashtag format
- Drag, pinch or scroll to position the photo; mobile dock with live preview
- Exports the best quality the photo allows (1080 to 2048 px square JPG, well under LinkedIn's 8 MB limit), downloaded on Save
- Get matched: optional email subscribe with explicit consent

## Privacy

Photos are processed entirely in the browser with the Canvas API. No image is uploaded or stored anywhere.

On Save, the site records the tag, frame style and traffic source. The server derives an approximate city from the connection and stores only the city, never the IP. Subscribers give an email and explicit consent.

## Data

Stored in Supabase (`sf_events`, `sf_subscribers`) via the `sf-track` edge function. Tag by city:

```sql
select * from sf_tag_by_city order by saves desc;
```

Microsoft Clarity: paste the project id into `CLARITY_ID` in `index.html`.

## Run it

It is a single static file. Open `index.html` in a browser, or host it on GitHub Pages:

1. Repo Settings > Pages
2. Source: Deploy from a branch
3. Branch: `main`, folder `/ (root)`
4. Save. The site appears at `https://hii2023.github.io/Linkedin/`
