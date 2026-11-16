# CaptionMind AI

CaptionMind AI turns an image or video into platform-specific social media captions.

## Features
- Image upload (PNG, JPEG, WebP) and video upload (MP4, WebM, MOV where browser support allows).
- Samples up to five frames from a video. Audio and speech are not transcribed.
- Six platforms: Instagram, LinkedIn, TikTok, Facebook, X and WhatsApp.
- WhatsApp output can be tailored for Status, Channels, direct messages or broadcasts.
- 50 writing tones, 100 reasoning lenses, audience/context controls and 3, 5 or 8 variations.
- Copy individual captions and hashtags.
- Deep navy / blue interface with Tollerman attribution.

## Run locally
1. Install Node.js 20 or newer.
2. Run `npm install`.
3. Copy `.env.example` to `.env`.
4. Add your OpenAI API key to `.env`.
5. Run `npm run dev`.

The API key is read only by the server-side API route. Do not add it to frontend code or commit `.env`.

## API
`POST /api/captions` accepts JSON:
- `platform`: instagram | linkedin | tiktok | facebook | x | whatsapp
- `tone`: one of the 50 supported tone labels
- `lenses`: array of reasoning lens names
- `count`: 3 | 5 | 8
- `length`: Short | Medium | Long
- `audience`, `context`, `whatsappFormat`
- `media`: array of `{ mimeType, data }`, where `data` is base64 without a data URL prefix.

Response: `{ captions: [{ text, angle, platformTip, hashtags }] }`.

## Important
This repository is public. Never commit API keys, credentials, customer data or private uploads.
