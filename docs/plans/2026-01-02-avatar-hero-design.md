# Avatar Hero Design

Date: 2026-01-02

## Overview

Add a personal avatar image to the home hero section to make the site feel more human and
welcoming. The avatar is a standalone identity element, not tied to any post content.

## Layout

- Home hero becomes a two-column layout on desktop: avatar on the left, intro text on the
  right.
- On mobile, the avatar stacks above the hero text.
- Avatar size ranges from 96–128px depending on screen width.
- The image is rendered as a circle with a soft border and gentle shadow for warmth.

## Implementation Notes

- Use `public/images/ryan.jpg` as the avatar source.
- Update `src/pages/index.astro` hero markup to include the avatar `img`.
- Add hero layout styles in `src/styles/global.css`.
- Image uses meaningful `alt` text and `loading="eager"`.

## Verification

- `npm run build` succeeds.
- Home hero displays avatar above the fold on desktop and mobile.

