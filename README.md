# web_demo

Personal multi-page portfolio website with a video hero, themed sections, and external media embeds.

## Pages

- `index.html`: landing page with hero video and category cards.
- `tech.html`: GitHub/project-focused page.
- `design.html`: design tools and workflow page.
- `personal.html`: Spotify + Letterboxd + social profile sections.

## Features

- Full-width looping hero video on homepage.
- Fixed glass-style navigation bar across pages.
- Card-based navigation from home to dedicated pages.
- Spotify album embeds in a 3x2 desktop grid on Personal.
- Letterboxd recent-watch feed pulled from RSS-to-JSON.
- Separate GitHub and LinkedIn cards with app-specific styling.
- Responsive behavior for tablet/mobile breakpoints.

## Project Structure

```text
web_demo/
	index.html
	tech.html
	design.html
	personal.html
	styles.css
	Source/
		Matias Mayans white.mp4
		spotify pfp.jpg
```

## Run Locally

Because of browser restrictions on local files, run with a local server instead of opening HTML directly.

### Option 1: Python

```powershell
cd "c:\Users\mamak\Documents\Programacion\Repos\web_demo"
python -m http.server 8080
```

Open `http://localhost:8080`.

## Customization

### Hero Video

Update the `src` in `index.html`:

```html
<video src="Source/Matias Mayans white.mp4" ...></video>
```

### Spotify Profile + Albums

- Spotify profile row is in `personal.html` (`.sp-header`).
- Album embeds are in the `.spotify-embeds` block.

### Letterboxd Username

In `personal.html`, update `data-letterboxd-user` on the Letterboxd section:

```html
<section class="media-card letterboxd-card" data-letterboxd-user="yourusername">
```

The feed loader uses:

```text
https://api.rss2json.com/v1/api.json?rss_url=https://letterboxd.com/<user>/rss/
```

### Social Links

GitHub and LinkedIn cards are in `personal.html` at the bottom of the Personal grid.

## Notes

- Spotify/Letterboxd embeds depend on external services and internet access.
- If posters do not appear, verify the Letterboxd RSS endpoint is accessible and not rate-limited.