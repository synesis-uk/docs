# Catchment API documentation instructions

## Purpose and audience

This is a technical reference for the Catchment API, not a set of how-to guides. Write for a developer who can send HTTP requests and read JSON. State behaviour precisely; leave out walkthroughs, tutorials and tips.

## Source of truth

- The API in the app repository (`/home/admin/catchment/app`, `lib/catchment-api/` and `app/v1/`) is the source of truth for parameters, responses, error codes and limits.
- Check behaviour against the running API or its code before documenting it. Do not infer it from older pages.
- `api-reference/openapi.json` must match the endpoints exactly. Update it in the same change as any endpoint change.
- `api-reference/metric-catalogue.mdx` was generated from `GET /v1/metrics`, with coverage and projection checked against real responses from the local API. Keep it in step with that endpoint, and recheck coverage against real responses when you change it.
- Use exact interface labels for app steps, such as **Account** > **Catchment API**.

## Content scope and structure

- `index.mdx` is the overview: endpoints, base URL, authentication, request and response conventions, errors, rate limits and coverage. Prefer tables.
- Each endpoint's page is generated from `api-reference/openapi.json`. Put its behaviour in the spec: the operation `description`, `x-mint.content` for longer rules, and parameter and schema descriptions. Do not add separate MDX pages for endpoints.
- Endpoints are grouped by OpenAPI tag. Add a navigation group in `docs.json` when a new tag is added.
- `api-reference/metric-catalogue.mdx` is the reference for metric keys.
- Document what the API does now. Leave out pricing, credits, SDKs and anything not yet built, and internal admin pages.

## Current review stage

The API is in internal preview. All content is local draft. Do not push to `main` without an explicit request: Mintlify publishes every push to `main`.

## Writing style

- Declarative and precise. One fact per sentence or table row.
- Use sentence case for titles and headings.
- Bold interface labels: **Account** > **Catchment API**.
- Use code formatting for parameters, keys, headers, paths, codes and values.
- No promotional language, filler or generic introductions.
- Do not invent behaviour, examples or permissions.

## Local workflow

- Pages are MDX files with YAML frontmatter. Navigation and settings live in `docs.json`.
- Run `npm install` once, then `npm run dev` for a local preview at `http://localhost:3000`.
- Run `npm run validate` and `npm run check:links` before completing a change.
- Review the rendered page, not only the MDX source.
