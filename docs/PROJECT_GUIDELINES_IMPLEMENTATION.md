# Project Guidelines Implementation

This document records where the project guidelines are represented in the site.

## Feature Audit

| Requirement | Implementation |
| --- | --- |
| Homepage with hero and CTA | `index.html:777-825`, including the hero image and `Discover Places` button |
| At least six listing cards | `index.html:887-949`, with six place cards |
| Individual details | Each place and restaurant card includes a name, description, category, and practical link |
| Navigation | `index.html:765-772`, with anchor links to every main section |
| Footer | `index.html:1220-1275`, including navigation and image attribution |
| Responsive layout | Grid and navigation breakpoints throughout the stylesheet, especially around `index.html:182-201`, `376-382`, and `664-670` |

The project is a static city guide rather than an e-commerce store, so shopping cart and checkout features are intentionally outside its scope.

## SEO

- `lang="en"` is set on the root `<html>` element at `index.html:2`.
- The page has a descriptive title at `index.html:6`.
- The page has a unique meta description at `index.html:7`.
- The page uses one main `<h1>` in the hero at `index.html:786`.
- Section headings use a logical `<h2>` and `<h3>` hierarchy.
- Internal links use descriptive labels such as `Discover Places`, `History`, and `Festive Calendar`.

## Accessibility

- Landmark, festival, gallery, and hero images have descriptive `alt` text.
- Decorative SVGs use `aria-hidden="true"`.
- Keyboard focus is visible through the `:focus-visible` rule at `index.html:72-75`.
- External map and attribution links use safe `target` and `rel` attributes.
- The mobile navigation has an accessible label at `index.html:761`.
- Reduced-motion preferences are respected at `index.html:77-79`.
- The page uses semantic `header`, `nav`, `main content sections`, `article`, and `footer` elements.

## Performance

- Off-screen images use `loading="lazy"`.
- Card images include explicit `width` and `height` attributes to reduce layout shift.
- Important landmark images are stored in `images/places/` so the page does not depend entirely on third-party image hosts.
- Festival assets are stored in `images/festivals/` where locally downloaded sources were available.
- The hero image remains eager because it is the main above-the-fold visual.
- CSS animation is disabled or reduced for users who request reduced motion.

## Responsive Testing

The stylesheet includes responsive layouts for:

- 320px and 425px mobile widths through single-column layouts and the mobile navigation.
- 600px widths for card grids.
- 700px widths for the facts strip and history timeline.
- 768px tablet layouts.
- 800px festival layouts.
- 900px laptop layouts.

The final browser check should cover 320px, 425px, 768px, 1024px, and 1440px.

## External Sources

- Landmark and festival photography is sourced from [Wikimedia Commons](https://commons.wikimedia.org/).
- Local asset sources include [Patan Durbar Square](https://commons.wikimedia.org/wiki/File:Patan_durbar_square.jpg), [Krishna Mandir](https://commons.wikimedia.org/wiki/File:Krishna_Mandir,_Lalitpur.jpg), [Patan Museum](https://commons.wikimedia.org/wiki/File:2023_-_Patan_Museum_-_Keshav_Narayan_Chowk_%26_Bidya_Mandira_-_img_0.jpg), [Golden Temple](https://commons.wikimedia.org/wiki/File:Golden_Temple_(Hiranya_Varna_Mahavihar).jpg), [Mahaboudha](https://commons.wikimedia.org/wiki/File:Mahaboudha_Sundhara_Patan_Lalitpur_Rajesh_Dhungana_(1).jpg), and [Ashok Chaitya](https://commons.wikimedia.org/wiki/File:Ashok_Chaitya_Pim_Bahal_11.jpg).
- Festival sources include [Rato Machindranath](https://commons.wikimedia.org/wiki/File:Rato_Machindranath_Jatra.jpg), [Tihar](https://commons.wikimedia.org/wiki/File:Sister_lighting_traditional_lamp_during_Tihar_festival.jpg), [Bisket Jatra](https://commons.wikimedia.org/wiki/File:Biska_Jatra_of_Bhaktapur.jpg), [Janai Purnima](https://commons.wikimedia.org/wiki/File:Janai_purnima_Festival_in_Nagarkot.jpg), [Gai Jatra](https://commons.wikimedia.org/wiki/File:Gai_Jatra_Kathmandu_Nepal_(5116171569).jpg), [Indra Jatra](https://commons.wikimedia.org/wiki/File:Chariot_procession,_Indra_Jatra,_Kathmandu_Durbar_Square.jpg), [Dashain](https://commons.wikimedia.org/wiki/File:Dashain_festival.jpg), and [Yomari Punhi](https://commons.wikimedia.org/wiki/File:Yomari_Punhi.jpg).
- Map links use the Google Maps search URL format and do not require an API key.

## Git Workflow

Changes were separated into real branches and commits:

- `feature/verified-place-images`: `feat: replace generic landmark photos with verified Patan images`
- `feature/card-map-links`: `feat: add useful map links to guide cards`
- `chore/quality-checks`: final documentation and quality fixes

The existing `.github/workflows/actions.yml` runs HTMLHint and deploys the static site through GitHub Pages on pushes to `main`.

## Known Limitations

- Festival dates are approximate because they follow a Nepali lunar calendar.
- Google Maps search links depend on Google’s current search results and do not provide guaranteed business hours.
- Some festival images show the wider Kathmandu Valley rather than Patan specifically because exact Patan documentation is limited on Wikimedia Commons.
- The static site does not currently provide live visitor information, dynamic dates, filtering, or an interactive map.

## Future Improvements

- Add a README with the live URL, technology stack, setup instructions, and screenshot.
- Add current opening times, ticket information, and walking guidance.
- Add a filter for places, food, and festivals.
- Add annual Nepali calendar date updates.
