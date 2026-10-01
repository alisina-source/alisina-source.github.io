# Ali — Professional Portfolio

Website: https://alisina-source.github.io

Only your GitHub account and collaborators you explicitly add can edit. Visitors can view the website and public files. Never upload passwords or private documents.

## Manage with forms

Open https://alisina-source.github.io/manage.html or click Manage portfolio on your website. Add experiences, education, albums, media and contact information using forms. Changes are temporary drafts in that browser tab; keep it open until you download them.

Click Download changes. Extract portfolio-changes.zip, then upload all extracted files to this repository with Add file → Upload files and Commit changes. Your live site updates after GitHub publishes. Only your GitHub account and any collaborators you add can publish changes. The form is publicly accessible; visitors can create their own local drafts but cannot change your published site without repository write access.

## Edit your profile and experience manually (optional)

Sign in, open `portfolio.json`, click the pencil (Edit), update text between quotation marks and commit changes to `main`. Keep valid JSON. GitHub Pages publishes updates automatically after a few minutes. Entries follow the order of the `entries` array; move an entry earlier to prioritize it.

## Upload photos and videos

On the repository page, choose Add file → Upload files, upload and commit. Then edit `portfolio.json`, adding a media object to the appropriate entry's `media` array:

```json
{"key":"car-inventory.jpg","type":"image/jpeg","name":"Car inventory","caption":"Cars I inventoried"}
```

Use the exact uploaded filename as `key`, and `video/mp4` for MP4 videos. The first file is the cover. Browser uploads allow up to 25 MiB per file. Export Live Photo motion as MP4, and convert HEIC stills to JPG.

## Albums below experience

Add a new entry with `section` set to `Work Albums` and `parentEntryId` matching its experience's `id`:

```json
{"id":"cars-album-1","section":"Work Albums","title":"Cars I inventoried","description":"Vehicle photographs and inventory records.","organization":"Absolute Auto Parts","period":"","parentEntryId":"experience-1","media":[{"key":"car-inventory.jpg","type":"image/jpeg","name":"Car inventory","caption":"Vehicle inventory"}]}
```

Optional organization fields: `organizationEmail`, `organizationWebsite`, `organizationPhone`, `organizationContact`, `organizationAddress`.
Optional profile contacts: `email`, `phone`, `whatsapp`, `linkedin`, `website`.

## Backup and rebuild

Code → Download ZIP saves all files, content and media. `website-source.zip` contains the React source. Extract, run `npm install` and `npm run build`, then publish the contents of `dist`. Before rebuilding, replace `public/portfolio.json` with the latest saved version and copy any newly uploaded media into `public/media`. Text changes and media uploads do not require rebuilding.

GitHub Pages: `main` branch, root folder. No Supabase or ChatGPT hosting dependency.
