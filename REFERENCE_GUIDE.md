# Reference & Ranking Guide

A decision aid for mining the **awesome-selfhosted** catalog when building your own AI vibe-coded apps. It answers three questions: *which references are worth studying, how strong is each category, and when should I copy vs. avoid a given app?*

> Grounded in the actual catalog data (`README.md` + `non-free.md`). Pair with `PROJECTS.md` for the raw name index.

---

## 1. How to use this guide

**Before you look — frame the borrow.**
Decide *what* you're copying: the product wedge ("alternative to X"), the data model, the UX flow, the deployment story, or actual code. Most self-hosted apps are not portable code (PHP/Ruby/Go/Elixir), but nearly all of them encode a reusable *decision*.

**While you look — read four things, in this order.**
1. The **positioning line** — every strong entry says "alternative to [incumbent]". That's your market framing.
2. The **license tag** — determines whether you can legally borrow code, not just ideas.
3. The **stack tag** — determines whether the architecture transfers to a modern TS/React/Convex stack.
4. The **`⚠` flag** — the catalog's own warning for an anti-feature (see §4).

**After you look — extract, don't clone.**
Write down the one pattern you'll reuse and the one mistake you'll avoid, then discard the repo. The value is in the decisions, not the source tree.

---

## 2. The scoring rubric

Score any candidate reference 0–5 on six dimensions; total /30, then divide by 3 for a /10:

| Dim | Question | 0 | 5 |
|-----|----------|---|---|
| **Health** | Actively maintained, recent releases, real community? | abandoned | thriving |
| **Deploy** | How easy to run? | 5 services + env hell | single binary / one Docker cmd |
| **Portability** | Do the *ideas* transfer to TS/React/Convex? | foreign stack, dated patterns | directly inspirational |
| **License** | How permissive? | proprietary/BUSL/SSPL | MIT/Apache |
| **Polish** | UX/DX quality | rough | delightful |
| **Docs** | Onboarding clarity | none | excellent |

**Category-level scores used in §3:**
- **Ref** — how trustworthy and complete the reference *set* is in that category (0–10).
- **Opp** — how much room a new AI-native entrant has (0–10; 10 = greenfield, 0 = saturated).

**Rule of thumb:** study **Ref ≥ 7**. Target **Opp ≥ 7**. The sweet spot is a category with a rich reference set *and* high opportunity — you learn fast and still have room to differentiate.

---

## 3. Catalog facts (grounded)

- **1,261** free projects · **94** non-free · **95** categories.
- **License distribution** (free): MIT 369 · AGPL-3.0 307 · GPL-3.0 227 · Apache-2.0 139 · GPL-2.0 108 · BSD-3 37 · MPL-2.0 18 · others small.
  - **AGPL dominates the "SaaS alternative" space** — fine to self-host, a real constraint if you fork into a hosted product.
- **Stack distribution**: Docker 710 · PHP 231 · Nodejs 210 · Python 158 · Go 151 · deb 105 · K8S 70 · Java 58 · C 56 · Rust 47 · C++ 41 · Ruby 34.
  - **Docker is table stakes.** For a TS/React builder, *Nodejs* apps are the most directly portable; *Go/Rust* is where the clean architecture lessons live; *PHP/Ruby* is where the product lessons live.
- **66 projects carry `⚠`** — the catalog's own marker for an anti-feature.

---

## 4. The `⚠` flag and "when to avoid"

awesome-selfhosted flags entries that have a caveat worth a second look. Treat `⚠` as **"reference with caution"**, never as "bad". Recurring reasons you'll find behind the flag:

- **Legal/ToS gray zones** — scrapers, downloaders, unofficial clients (e.g. the media-management cluster: `youtube-dl` frontends, downloaders).
- **Trademark/brand risk** — unauthorized or confusing client implementations.
- **Resource-heavy / aggressive** — projects that can hog bandwidth or hardware.
- **Security-sensitive surfaces** — things exposed to the internet by default.

**Avoid (as a code reference) when:** the license is proprietary/BUSL/SSPL and you plan to fork; the stack is a dead end for your team; the flags point at the project's *core* (not a peripheral feature); or the project is a thin wrapper you can build yourself in an afternoon.

**Still worth studying even when flagged:** the *positioning*, the *onboarding flow*, and the *feature scope choices* — those carry no legal risk.

---

## 5. Category scorecards

`Ref` = reference-set quality · `Opp` = opportunity for a new AI-native entrant.

| Category | Ref | Opp | Best references | Verdict |
|---|:--:|:--:|---|---|
| Analytics | 9 | 6 | Plausible, Umami, PostHog, GoatCounter | Crowded but evergreen; differentiate on privacy/UX/AI insights. |
| Archiving & Digital Preservation | 7 | 6 | ArchiveBox, Wallabag, Wayback | Strong capture pipelines; consumer UX is weak. |
| Automation | 8 | 7 | Activepieces, changedetection.io, Healthchecks | Rich references; room for AI-native "describe the workflow" builders. |
| Blogging Platforms | 8 | 5 | Ghost, WriteFreely, HTMLy | Mature; win on publishing+membership bundles. |
| Booking & Scheduling | 7 | 7 | Rallly, Cal.diy, Easy!Appointments | No-signup flows are the differentiator. |
| Bookmarks & Link Sharing | 9 | 6 | linkding, Linkwarden, Karakeep | Careful, well-built space; AI auto-filing is the opening. |
| Calendar & Contacts | 7 | 5 | Radicale, Baïkal, SabreDAV | Protocol plumbing; low differentiation. |
| Communication — Custom | 8 | 7 | ntfy, Gotify, Novu, Apprise | Notifications are a strong infra wedge. |
| Communication — Email (full) | 8 | 6 | docker-mailserver, Mailcow, Mailu | High bar; operational complexity is the moat. |
| Communication — Email (MDA/MTA) | 8/9 | 3 | Dovecot, Postfix, Maddy | Deep plumbing; don't reinvent. |
| Communication — Mailing lists | 8 | 6 | Listmonk, Mautic, phpList | Listmonk is the modern reference. |
| Communication — Webmail | 8 | 4 | Roundcube, SnappyMail, Cypht | Settled; win via AI triage/summaries. |
| Communication — IRC | 8 | 3 | Ergo, The Lounge, Kiwi IRC | Niche but well-served. |
| Communication — SIP | 8 | 4 | Asterisk, FreeSWITCH, FusionPBX | Expert domain; high barrier. |
| Communication — Social/Forums | 8 | 7 | Mastodon, Lemmy, Discourse, Flarum | Federation is hard; HTTP-based spaces still open. |
| Communication — Video Conferencing | 8 | 6 | Jitsi Meet, BigBlueButton, Galene | WebRTC infra is the moat; join-flow UX is copyable. |
| Communication — XMPP | 8/7 | 3 | Prosody, ejabberd, Converse.js | Protocol-complete; low opportunity. |
| Community-Supported Agriculture | 7 | 6 | Open Food Network, Foodsoft, juntagrico | Underserved niche with clear workflows. |
| Conference Management | 8 | 5 | pretalx, indico, OpenSlides | Specialist; strong references. |
| CMS | 9 | 6 | WordPress, Payload CMS, Strapi, Wagtail | Huge incumbents; headless/AI-editorial is the opening. |
| CRM | 7 | 7 | Twenty, EspoCRM, SuiteCRM | Modern TS CRM references are rare — big opening. |
| Database Management | 8 | 7 | Baserow, Mathesar, Datasette, Adminer | "Friendly UI over data" is a repeatable wedge. |
| DNS | 9 | 5 | Pi-hole, AdGuard Home, blocky | Excellent references; hard to differentiate. |
| Document Management | 8 | 7 | Paperless-ngx, Documenso, Stirling-PDF | Ingestion+AI is the frontier. |
| Document Management — E-books | 8 | 5 | Calibre Web, Kavita, Komga | Well-served readers; metadata/UX openings. |
| Institutional Repositories | 8 | 4 | DSpace, InvenioRDM, Islandora | Academic-only. |
| Integrated Library Systems | 8 | 4 | Koha, Evergreen, RERO ILS | Specialist institutions only. |
| E-commerce | 8 | 7 | MedusaJs, Saleor, Vendure, WooCommerce | Headless is the modern wedge; Playwright of refs. |
| Feed Readers | 8 | 5 | Miniflux, FreshRSS, Tiny Tiny RSS | AI summarization is the obvious opening. |
| File Transfer & Sync | 9 | 5 | Nextcloud, Syncthing, Seafile | Deep moats; hard to enter. |
| Object Storage & File Servers | 8 | 5 | GarageHQ, SeaweedFS, Harbor | Infra; study architecture only. |
| Peer-to-peer Filesharing | 8 | 5 | qBittorrent, Transmission, slskd | Protocol-bound; UI openings only. |
| Single-click Upload | 8 | 6 | Zipline, Chibisafe, Pingvin Share X | Small enough to clone well; share-UX wins. |
| Web-based File Managers | 8 | 6 | Filestash, FileGator, copyparty | "One UI over many backends" wedge. |
| Games | 7 | 6 | Luanti, Mindustry, OpenTTD | Deep-tech references; not web-app adjacent. |
| Game Admin & Control Panels | 8 | 6 | Pterodactyl, Crafty Controller, LinuxGSM | Good control-panel UX references. |
| Genealogy | 7 | 6 | Gramps Web, webtrees, GeneWeb | Underserved; data-model lesson. |
| Generative AI (GenAI) | 7 | 9 | Ollama, Open-WebUI, LibreChat, Langfuse | Youngest category; fastest-moving; highest opportunity. |
| Groupware | 8 | 6 | SOGo, Zimbra, Tracim | Heavy suites; componentization is the opening. |
| Health & Fitness | 7 | 6 | OpenEMR, wger, FitTrackee | Compliance-heavy; niche trackers easier. |
| Human Resources Management | 7 | 6 | Frappe HR, MintHCM | Enterprise workflows; modest references. |
| Internet of Things | 9 | 6 | Home Assistant, Node RED, openHAB | Integration catalogs are the moat. |
| Inventory Management | 8 | 6 | Inventree, Part-DB, HomeBox | Barcode/parts workflows; solid references. |
| Knowledge Management | 8 | 7 | AFFiNE, SiYuan, TeamMapper | Collab/doc convergence; CRDT complexity. |
| Learning & Courses | 9 | 6 | Moodle, Canvas LMS, Chamilo | Standards-bound (SCORM/LTI); rich refs. |
| Manufacturing | 8 | 5 | Octoprint, Fluidd, Mainsail | Hardware-coupled; UI lessons only. |
| Maps & GPS | 8 | 6 | Nominatim, GraphHopper, Traccar | Geo infra is hard; trackers are friendlier. |
| Media Management | 8 | 5 | Sonarr, Radarr, Lidarr, Ombi | Highly polished niche; legal gray edges. |
| Media Streaming — Audio | 9 | 5 | Navidrome, Audiobookshelf, Funkwhale | Excellent references; mature. |
| Media Streaming — Multimedia | 8 | 5 | Jellyfin, Kodi, Gerbera | Deep incumbents; hard entry. |
| Media Streaming — Video | 8 | 6 | PeerTube, Invidious, Owncast | P2P/federation moats; live is open. |
| Miscellaneous | 7 | 6 | 2FAuth, Penpot, Infisical, Reactive Resume | Grab-bag; single-purpose utilities shine. |
| Money, Budgeting & Management | 8 | 7 | Firefly III, Ghostfolio, BTCPay, Actual | Rules/imports are the hard, valuable part. |
| Network Utilities | 8 | 6 | NetAlertX, MySpeed, Speedtest Tracker | Observability UI is copyable. |
| Note-taking & Editors | 9 | 6 | Joplin, HedgeDoc, SilverBullet, CryptPad | Rich refs; collaboration is the frontier. |
| Office Suites | 8 | 5 | CryptPad, ONLYOFFICE, Collabora, Grist | Format compatibility is the moat. |
| Password Managers | 9 | 4 | Vaultwarden, Bitwarden, Passbolt | Security bar is extreme; borrow UX only. |
| Pastebins | 8 | 6 | PrivateBin, Yopass, Opengist | Tiny, cloneable; zero-knowledge is the hook. |
| Personal Dashboards | 8 | 6 | Homepage, Homarr, Dashy, LinkStack | Glue apps; AI "auto-configure my services" opening. |
| Photo Galleries | 8 | 5 | Immich, PhotoPrism, Lychee | Immich set the bar; ML search differentiates. |
| Polls & Events | 8 | 7 | Formbricks, Fider, Mobilizon, LimeSurvey | In-app feedback/surveys is a strong wedge. |
| Proxy | 8 | 4 | Traefik, Caddy, imgproxy, Pomerium | Infra; study config UX. |
| Recipe Management | 8 | 6 | Mealie, RecipeSage, Bar Assistant | Solid refs; AI import/scaling is the opening. |
| Remote Access | 8 | 6 | Guacamole, MeshCentral, Firezone | Zero-trust UX is the modern angle. |
| Resource Planning (ERP) | 8 | 6 | ERPNext, Odoo, Dolibarr, grocy | Huge scope; modular entrant can win. |
| Search Engines | 8 | 6 | MeiliSearch, Typesense, OpenSearch, Fess | Retrieval infra; DX is the differentiator. |
| Self-hosting Solutions | 8 | 6 | YunoHost, OpenMediaVault, FreedomBox | Meta-layer; onboarding is everything. |
| API Management | 8 | 6 | Kong, Hasura, Tyk, Svix | Gateways/webhooks; strong refs. |
| Feature Toggle | 8 | 6 | Flagsmith, Flipt, Featbit | Small, well-defined; SDK DX wins. |
| IDE & Tools | 8 | 7 | code-server, JupyterLab, Langfuse, Coder | Dev-tooling is hot; AI-assisted opening. |
| Localization | 8 | 5 | Weblate, Tolgee, Traduora | Git-integrated niche; AI translation opening. |
| Low Code | 7 | 8 | Appsmith, PocketBase, Appwrite, ToolJet | AI-generated internal tools is a huge opening. |
| Project Management | 9 | 6 | GitLab, Gitea, Forgejo, Plane | Mature; AI-native PM is the frontier. |
| Software Dev — Testing | 6 | 8 | Bencher, WebHook Tester, Request Inbox | Thin reference set; wide-open. |
| Task Management | 8 | 6 | Vikunja, AppFlowy, Kanboard, Wekan | Well-served; local-first/AI is the angle. |
| Ticketing | 8 | 6 | Zammad, FreeScout, GlitchTip, MantisBT | AI triage is the opening. |
| Time Tracking | 8 | 6 | Kimai, solidtime, ActivityWatch, Wakapi | Solid refs; auto-tracking is the opening. |
| Travel Organization | 5 | 8 | Surmai | Nearly greenfield — one entrant. |
| URL Shorteners | 8 | 6 | Shlink, Kutt, YOURLS | Tiny and cloneable; analytics is the hook. |
| Video Surveillance | 8 | 6 | Frigate, Zoneminder, Viseron | Edge-AI reference; hardware-gated. |
| Web Servers | 9 | 4 | Nginx, Caddy, Traefik, HAProxy | Extremely mature; don't enter. |
| Wikis | 9 | 6 | BookStack, Wiki.js, Dokuwiki, XWiki | Rich refs; AI authoring is the opening. |

*Excluded (cross-linked umbrella headers with no direct entries): Backup, Federated Identity & Auth, Identity Management, Media Streaming, Monitoring & Status Pages, Software Development, Static Site Generators, VPN, CI/CD, FaaS & Serverless.*

---

## 6. Application TL;DR cards

Each card: what it is, **when to reference it**, **when to avoid it**, and what to weigh **before** and **after** studying.

### Analytics

**Plausible Analytics** — `AGPL-3.0` · Elixir · [source](https://github.com/plausible/analytics)
- ✅ **Reference when:** designing a lightweight, privacy-first analytics product; its single-metric dashboard and one-script onboarding are the model.
- ⛔ **Avoid when:** you need portable code — Elixir/Phoenix won't transfer to a TS stack, and AGPL constrains a hosted fork.
- 🔎 **Before:** settle your license/distribution model; decide copy-UX vs copy-code.
- 🧭 **After:** adopt the "one tiny script → instant dashboard" flow and keep the metric surface deliberately small.

**Umami** — `MIT` · Nodejs/Docker · [source](https://github.com/umami-software/umami)
- ✅ **Reference when:** you want a Node/Next.js privacy-analytics reference with a friendly license; shareable dashboards.
- ⛔ **Avoid when:** you need funnels, session replay, or enterprise depth.
- 🔎 **Before:** compare its event/pageview data model to what you'll store.
- 🧭 **After:** reuse the public share-link dashboard pattern as a growth loop.

**PostHog** — `MIT` · Python · [source](https://github.com/posthog/posthog)
- ✅ **Reference when:** studying how to bundle analytics + feature flags + session replay + experiments into one product.
- ⛔ **Avoid when:** you want a code reference for a small app — it's a Django/ClickHouse monolith.
- 🔎 **Before:** note the infrastructure weight (Postgres + ClickHouse + Kafka).
- 🧭 **After:** steal the "all-in-one product-ops suite" bundling strategy as a wedge.

**GoatCounter** — `EUPL-1.2` · Go · [source](https://github.com/arp242/goatcounter)
- ✅ **Reference when:** you want the minimal, single-binary, cookie-free analytics archetype with excellent docs.
- ⛔ **Avoid when:** users expect real-time segmentation or heavy dashboards.
- 🔎 **Before:** EUPL is copyleft — verify compatibility for your use.
- 🧭 **After:** study its tiny footprint as a deliberate differentiator.

### Capture & bookmarks

**ArchiveBox** — `MIT` · Python/Docker · [source](https://github.com/ArchiveBox/ArchiveBox)
- ✅ **Reference when:** building a "save anything" capture pipeline (HTML/screenshots/media) from many sources.
- ⛔ **Avoid when:** you need a polished consumer UX or low resource use.
- 🔎 **Before:** plan storage, queueing, and extraction dependencies.
- 🧭 **After:** reuse the bookmarklet + import + API ingest triad.

**Karakeep** — `AGPL-3.0` · Docker · [source](https://github.com/karakeep-app/karakeep)
- ✅ **Reference when:** building an **AI-assisted** capture app — auto-tagging and summarization are core.
- ⛔ **Avoid when:** AGPL doesn't fit your product's distribution.
- 🔎 **Before:** study how it wires LLMs into tagging/enrichment.
- 🧭 **After:** adopt "the AI files it for you" as the UX promise; lead with search.

**linkding** — `MIT` · Docker · [source](https://github.com/sissbruecker/linkding)
- ✅ **Reference when:** you want the simplest possible bookmark tool — minimal, fast, single-user, Pi-friendly.
- ⛔ **Avoid when:** you need multi-user collaboration.
- 🔎 **Before:** note it's Django + SQLite; the ideas transfer, the code doesn't.
- 🧭 **After:** study its browser-extension + tag + archive model.

### Automation

**Activepieces** — `MIT` · Docker · [source](https://github.com/activepieces/activepieces)
- ✅ **Reference when:** building a no-code workflow/automation builder; study the visual flow editor and connector abstraction.
- ⛔ **Avoid when:** you need Zapier-scale connector depth.
- 🔎 **Before:** understand the piece/flow/trigger data model.
- 🧭 **After:** reuse the "open-source, easy self-host, friendly license" positioning.

**changedetection.io** — `Apache-2.0` · Python/Docker · [source](https://github.com/dgtlmoon/changedetection.io)
- ✅ **Reference when:** building any "watch this and tell me when it changes" feature; selector-based diffing + notification fan-out.
- ⛔ **Avoid when:** you need high-scale distributed scheduling.
- 🔎 **Before:** design your notification providers up front.
- 🧭 **After:** copy the per-watch configuration UX and visual diff view.

**Healthchecks** — `BSD-3-Clause` · Python/Docker · [source](https://github.com/healthchecks/healthchecks)
- ✅ **Reference when:** designing a cron/heartbeat "dead-man's switch" monitor with a dead-simple ping API.
- ⛔ **Avoid when:** you need full observability/APM.
- 🔎 **Before:** understand ping URLs, grace periods, and schedules.
- 🧭 **After:** reuse the alert-channel matrix (email/webhook/Slack/etc.).

### Booking

**Rallly** — `AGPL-3.0` · Nodejs/Docker · [source](https://github.com/lukevella/rallly)
- ✅ **Reference when:** building scheduling/polling on a modern TS stack (Next.js + Prisma + tRPC) with a clean "Doodle alternative" story.
- ⛔ **Avoid when:** AGPL is a blocker or you need enterprise calendar sync.
- 🔎 **Before:** study its auth/session and no-signup participant flow.
- 🧭 **After:** steal the "participate without an account" flow — it's a conversion win.

### Content & CMS

**Ghost** — `MIT` · Nodejs · [source](https://github.com/TryGhost/Ghost)
- ✅ **Reference when:** building publishing + paid memberships + newsletters as one product with a strong API.
- ⛔ **Avoid when:** you want a general-purpose framework — it's opinionated.
- 🔎 **Before:** note its memberships/Stripe design.
- 🧭 **After:** adopt the "publishing + membership in one box" bundling.

**Payload CMS** — `MIT` · Nodejs · [source](https://github.com/payloadcms/payload)
- ✅ **Reference when:** building content apps in TypeScript — code-first schema, local API, Next.js integration. Highly portable.
- ⛔ **Avoid when:** you need a no-code editor or a large plugin marketplace.
- 🔎 **Before:** decide code-first vs UI-first content modeling.
- 🧭 **After:** mimic its "your database, your schema, generated admin UI" pitch.

**Strapi** — `MIT` · Nodejs · [source](https://github.com/strapi/strapi)
- ✅ **Reference when:** you want a headless CMS reference with a mature admin UX and plugin ecosystem.
- ⛔ **Avoid when:** you want a small footprint; major-version migrations are heavy.
- 🔎 **Before:** check which plugins are paid/open-core.
- 🧭 **After:** study its content-type builder as an editing UX.

### Email & notifications

**Listmonk** — `AGPL-3.0` · Go/Docker · [source](https://github.com/knadh/listmonk)
- ✅ **Reference when:** building newsletters/campaigns; single-binary, high-performance, clean admin.
- ⛔ **Avoid when:** you need drip/marketing automation depth.
- 🔎 **Before:** understand its subscriber/segment/template model.
- 🧭 **After:** copy CSV import + bounce/complaint handling.

**SimpleLogin** — `MIT` · Docker/Python · [source](https://github.com/simple-login/app)
- ✅ **Reference when:** building email alias privacy features; study alias creation and forwarding.
- ⛔ **Avoid when:** you expected a full mail server — it's a client-side forwarding layer.
- 🔎 **Before:** MX/DNS requirements are real; plan them.
- 🧭 **After:** reuse the browser-extension "create alias inline" flow.

**ntfy** — `Apache-2.0`/`GPL-2.0` · Go · [source](https://github.com/binwiederhier/ntfy)
- ✅ **Reference when:** adding push notifications with the simplest possible model (HTTP PUT/POST to a topic).
- ⛔ **Avoid when:** you need guaranteed delivery or compliance.
- 🔎 **Before:** topic model is open by default — design access control.
- 🧭 **After:** steal the "curl and you're notified" DX.

**Novu** — `MIT` · Docker/Nodejs · [source](https://github.com/novuhq/novu)
- ✅ **Reference when:** building multi-channel notification infrastructure (one API → email/SMS/push/chat).
- ⛔ **Avoid when:** your app is small — it's heavyweight.
- 🔎 **Before:** understand provider abstraction + workflows.
- 🧭 **After:** reuse the "one API, many channels" positioning.

### Chat, social & video

**Rocket.Chat** — `MIT` · Nodejs · [source](https://github.com/RocketChat/Rocket.Chat)
- ✅ **Reference when:** building team chat; study rooms/threads/apps marketplace and the Slack-alternative onboarding.
- ⛔ **Avoid when:** you want low dependencies — it's heavy (Meteor).
- 🔎 **Before:** check the enterprise-edition boundary.
- 🧭 **After:** study its migration/import-from-Slack flow.

**Zulip** — `Apache-2.0` · Python · [source](https://github.com/zulip/zulip)
- ✅ **Reference when:** you need a **UX differentiator** — topic/thread-first chat is a genuine "why not Slack".
- ⛔ **Avoid when:** you need a JS code reference.
- 🔎 **Before:** understand the stream/topic threading model.
- 🧭 **After:** adopt topic threading as your core positioning.

**Mastodon** — `AGPL-3.0` · Ruby · [source](https://github.com/mastodon/mastodon)
- ✅ **Reference when:** building federated/social features (ActivityPub) or studying moderation tooling.
- ⛔ **Avoid when:** you can't commit to protocol complexity or Ruby.
- 🔎 **Before:** ActivityPub is a long-term investment.
- 🧭 **After:** study its moderation UX as a competitive wedge.

**Lemmy** — `AGPL-3.0` · Rust/Docker · [source](https://github.com/LemmyNet/lemmy)
- ✅ **Reference when:** building link-aggregator/community features; Rust performance + federation.
- ⛔ **Avoid when:** you need a mature, low-bug reference.
- 🔎 **Before:** plan federation + moderation from day one.
- 🧭 **After:** copy its Reddit-alternative framing.

**Discourse** — `GPL-2.0` · Docker · [source](https://github.com/discourse/discourse)
- ✅ **Reference when:** building forums/community; the gold standard for trust levels, badges, moderation, and SEO.
- ⛔ **Avoid when:** you want light resources — Ruby + Redis + Postgres is heavy.
- 🔎 **Before:** understand the trust-level system.
- 🧭 **After:** steal trust levels + badges for engagement loops.

**Jitsi Meet** — `Apache-2.0` · Nodejs/Docker · [source](https://github.com/jitsi/jitsi-meet)
- ✅ **Reference when:** adding WebRTC video; study scalable SFU design and the no-account join flow.
- ⛔ **Avoid when:** you need recording/compliance without self-managing infra.
- 🔎 **Before:** SFU + TURN infrastructure is nontrivial.
- 🧭 **After:** copy the "instant room, no login" experience.

### CRM & data

**Twenty** — `AGPL-3.0` · Docker · [source](https://github.com/twentyhq/twenty)
- ✅ **Reference when:** you want a **modern TS/React CRM** reference — sleek design, plugin architecture.
- ⛔ **Avoid when:** you need proven enterprise maturity.
- 🔎 **Before:** it's young — check roadmap/stability.
- 🧭 **After:** study its Notion-like record/data model.

**Baserow** — `MIT` · Docker · [source](https://gitlab.com/baserow/baserow)
- ✅ **Reference when:** building spreadsheet-database UIs; study grid UX, formulas, and the Airtable-alternative positioning.
- ⛔ **Avoid when:** you want a pure library — it's Django/Vue.
- 🔎 **Before:** check open-core tier boundaries.
- 🧭 **After:** reuse the template gallery as an adoption hook.

**Mathesar** — `GPL-3.0` · Docker/Python · [source](https://github.com/mathesar-foundation/mathesar)
- ✅ **Reference when:** giving non-technical users a UI over an existing Postgres DB.
- ⛔ **Avoid when:** you need NoSQL or turnkey app building.
- 🔎 **Before:** study its schema-introspection approach.
- 🧭 **After:** copy the "your existing DB, friendly UI, no migration" pitch.

### Documents

**Paperless-ngx** — `GPL-3.0` · Python/Docker · [source](https://github.com/paperless-ngx/paperless-ngx)
- ✅ **Reference when:** building document ingestion + OCR + auto-tagging pipelines.
- ⛔ **Avoid when:** you need a light footprint or consumer-grade simplicity.
- 🔎 **Before:** plan OCR/compute and storage costs.
- 🧭 **After:** reuse the correspondents/tags/document-type model.

**Documenso** — `AGPL-3.0` · Nodejs/Docker · [source](https://github.com/documenso/documenso)
- ✅ **Reference when:** building e-signature in a modern TS stack with a DocuSign-alternative story.
- ⛔ **Avoid when:** you can't validate legal compliance in your target markets.
- 🔎 **Before:** signing flows carry real legal/audit requirements.
- 🧭 **After:** study its signing UX and audit-trail certificates.

**Stirling-PDF** — `Apache-2.0` · Docker/Java · [source](https://github.com/Stirling-Tools/Stirling-PDF)
- ✅ **Reference when:** you need a pattern for "many small local file operations" behind one UI; great feature-scope reference.
- ⛔ **Avoid when:** you want a JS codebase.
- 🔎 **Before:** map which operations really need a server.
- 🧭 **After:** copy its "private, local, no-upload" privacy promise.

### Commerce

**MedusaJs** — `MIT` · Nodejs · [source](https://github.com/medusajs/medusa)
- ✅ **Reference when:** building headless commerce in TypeScript with a Next.js storefront — the most portable commerce reference here.
- ⛔ **Avoid when:** you need a turnkey storefront.
- 🔎 **Before:** note the v2 modular rewrite — follow the current architecture.
- 🧭 **After:** copy the "headless + developer-first commerce" wedge.

**Saleor** — `BSD-3-Clause` · Docker/Python · [source](https://github.com/saleor/saleor)
- ✅ **Reference when:** studying API-first/GraphQL commerce design at enterprise scale.
- ⛔ **Avoid when:** you want a JS-only stack or simple setup.
- 🔎 **Before:** GraphQL + Django is a heavy commitment.
- 🧭 **After:** study its API-first product modeling.

### Sync, files & uploads

**Nextcloud** — `AGPL-3.0` · PHP · [source](https://github.com/nextcloud/server)
- ✅ **Reference when:** studying a file-sync **suite** with an app store and federation.
- ⛔ **Avoid when:** you want a lean reference architecture — it's PHP and huge.
- 🔎 **Before:** federation/encryption concepts add real complexity.
- 🧭 **After:** steal the app-ecosystem model as a platform strategy.

**Syncthing** — `MPL-2.0` · Go · [source](https://github.com/syncthing/syncthing)
- ✅ **Reference when:** studying peer-to-peer, no-central-server sync architecture and device pairing.
- ⛔ **Avoid when:** you need browser-accessible storage (it's local-first).
- 🔎 **Before:** NAT traversal + relay complexity is significant.
- 🧭 **After:** copy its device-pairing/QR onboarding UX.

**Zipline** — `MIT` · Docker/Nodejs · [source](https://github.com/diced/zipline)
- ✅ **Reference when:** building file/image upload with API keys and ShareX integration; clean React UI + API.
- ⛔ **Avoid when:** you need enterprise permissions/quotas.
- 🔎 **Before:** choose storage backends up front.
- 🧭 **After:** study its keyboard-first / ShareX upload workflow.

### AI

**Ollama** — `MIT` · Docker · [source](https://github.com/ollama/ollama)
- ✅ **Reference when:** adding local LLM serving; study model management and a dead-simple API.
- ⛔ **Avoid when:** you need production multi-tenant GPU scaling.
- 🔎 **Before:** hardware/GPU requirements are real.
- 🧭 **After:** copy the "one command to run a model" DX.

**Open-WebUI** — `BSD-3-Clause` · Docker/Python · [source](https://github.com/open-webui/open-webui)
- ✅ **Reference when:** building an AI chat UI over multiple providers; feature-rich (RAG, models, users).
- ⛔ **Avoid when:** you need commercial support.
- 🔎 **Before:** plan provider abstraction early.
- 🧭 **After:** study its model-switching and document-chat features.

**LibreChat** — `MIT` · Nodejs/Docker · [`⚠`] · [source](https://github.com/danny-avila/LibreChat)
- ✅ **Reference when:** studying a multi-provider ChatGPT-style UI with auth, plugins, and agents.
- ⛔ **Avoid when:** resources matter (it's heavy) or you haven't checked the `⚠` flag.
- 🔎 **Before:** understand the flagged caveat; plan for resource use.
- 🧭 **After:** copy the provider-agnostic setup experience.

**Langfuse** — `MIT` · Docker · [source](https://github.com/langfuse/langfuse)
- ✅ **Reference when:** building LLM observability — tracing, prompt management, evaluations. The reference for LLM ops.
- ⛔ **Avoid when:** you don't operate LLM features.
- 🔎 **Before:** decide trace retention/privacy policy.
- 🧭 **After:** adopt "observability for AI apps" as a category wedge.

### IoT, knowledge, media

**Home Assistant** — `Apache-2.0` · Python/Docker · [source](https://github.com/home-assistant/core)
- ✅ **Reference when:** studying integration-heavy platforms — entity/state modeling and a massive integration catalog.
- ⛔ **Avoid when:** you want a light reference — it's enormous.
- 🔎 **Before:** the integration framework is a real investment.
- 🧭 **After:** study how the integration catalog became a moat.

**AFFiNE** — `MIT`/`AGPL-3.0` · Docker · [source](https://github.com/toeverything/AFFiNE)
- ✅ **Reference when:** building collaborative docs + whiteboard; study CRDT-driven real-time collaboration.
- ⛔ **Avoid when:** dual licensing is a problem.
- 🔎 **Before:** CRDT/local-first architecture is complex.
- 🧭 **After:** copy the "docs + canvas in one" positioning.

**Jellyfin** — `GPL-2.0` · C#/Docker · [source](https://github.com/jellyfin/jellyfin)
- ✅ **Reference when:** studying an ecosystem play — server + many clients + plugin catalog.
- ⛔ **Avoid when:** you need a web-only reference.
- 🔎 **Before:** note the client-fleet maintenance burden.
- 🧭 **After:** study its community fork governance as a model.

**Audiobookshelf** — `GPL-3.0` · Docker/Nodejs · [source](https://github.com/advplyr/audiobookshelf)
- ✅ **Reference when:** building media streaming with progress-sync across mobile apps.
- ⛔ **Avoid when:** you only need a simple player.
- 🔎 **Before:** understand progress-sync data model.
- 🧭 **After:** study its first-party mobile app strategy.

**Navidrome** — `GPL-3.0` · Docker/Go · [source](https://github.com/navidrome/navidrome)
- ✅ **Reference when:** building a lightweight media server; Subsonic-API compatibility is a smart leverage play.
- ⛔ **Avoid when:** you need video.
- 🔎 **Before:** decide protocol compatibility vs custom API.
- 🧭 **After:** copy "be compatible with an existing client ecosystem".

**PeerTube** — `AGPL-3.0` · Nodejs · [source](https://github.com/Chocobozzz/PeerTube)
- ✅ **Reference when:** building decentralized/P2P video; browser-embedded BitTorrent is a strong technical reference.
- ⛔ **Avoid when:** you need simple hosting.
- 🔎 **Before:** P2P + federation is a large project.
- 🧭 **After:** study its federation/moderation model.

### Security, money, utilities

**Vaultwarden** — `GPL-3.0` · Rust/Docker · [source](https://github.com/dani-garcia/vaultwarden)
- ✅ **Reference when:** studying the "lightweight compatible reimplementation" strategy (Bitwarden API in Rust).
- ⛔ **Avoid when:** you need official support or are building security-sensitive software casually.
- 🔎 **Before:** security review is non-negotiable in this domain.
- 🧭 **After:** copy the "drop-in lighter alternative" positioning.

**PrivateBin** — `Zlib` · PHP · [source](https://github.com/PrivateBin/PrivateBin)
- ✅ **Reference when:** building zero-knowledge/encrypted sharing features.
- ⛔ **Avoid when:** you need a modern codebase reference.
- 🔎 **Before:** understand client-side encryption guarantees.
- 🧭 **After:** reuse the "server knows nothing" security promise.

**Immich** — `AGPL-3.0` · Docker · [source](https://github.com/immich-app/immich)
- ✅ **Reference when:** building photo/video backup with first-party mobile apps and ML-powered search.
- ⛔ **Avoid when:** resources are constrained.
- 🔎 **Before:** needs real hardware (and ML models).
- 🧭 **After:** steal the Google-Photos-alternative framing and timeline UX.

**Firefly III** — `AGPL-3.0` · PHP/Docker · [source](https://github.com/firefly-iii/firefly-iii)
- ✅ **Reference when:** building personal finance with a powerful rules engine and bank imports.
- ⛔ **Avoid when:** you need a simple UX — it's dense and feature-heavy.
- 🔎 **Before:** understand its double-entry account/transaction model.
- 🧭 **After:** reuse the rules engine + import pipeline.

**Ghostfolio** — `AGPL-3.0` · Nodejs/Docker · [source](https://github.com/ghostfolio/ghostfolio)
- ✅ **Reference when:** building portfolio/wealth tracking in TS; clean data-visualization reference.
- ⛔ **Avoid when:** you need real-time trading.
- 🔎 **Before:** market-data licensing matters.
- 🧭 **After:** study its allocation/chart UX.

**Formbricks** — `AGPL-3.0` · Nodejs/Docker · [source](https://github.com/formbricks/formbricks)
- ✅ **Reference when:** building surveys/feedback embedded inside an app; modern TS + "experience management" framing.
- ⛔ **Avoid when:** AGPL doesn't fit.
- 🔎 **Before:** plan in-app targeting/triggers.
- 🧭 **After:** copy in-app micro-survey placement.

**Caddy** — `Apache-2.0` · Go · [source](https://github.com/caddyserver/caddy)
- ✅ **Reference when:** studying configuration ergonomics and automatic HTTPS.
- ⛔ **Avoid when:** you need advanced L7 routing (consider Traefik/Nginx).
- 🔎 **Before:** compare with your deployment topology.
- 🧭 **After:** adopt "HTTPS by default" as a product promise.

**Traefik** — `MIT` · Go · [source](https://github.com/traefik/traefik)
- ✅ **Reference when:** dynamic service discovery / reverse proxy for containers; study the dashboard + label config.
- ⛔ **Avoid when:** you want simple static config.
- 🔎 **Before:** understand provider/label complexity.
- 🧭 **After:** copy auto-discovery as the core value.

**Nginx Proxy Manager** — `MIT` · Docker · [source](https://github.com/NginxProxyManager/nginx-proxy-manager)
- ✅ **Reference when:** building a friendly GUI over complex infrastructure — the "make hard things one-click" pattern.
- ⛔ **Avoid when:** you need advanced raw config.
- 🔎 **Before:** certificate automation is the tricky part.
- 🧭 **After:** copy the "easy reverse proxy" positioning.

**MeiliSearch** — `MIT` · Rust/Docker · [source](https://github.com/meilisearch/MeiliSearch)
- ✅ **Reference when:** adding instant, typo-tolerant search; study search DX and API design.
- ⛔ **Avoid when:** you need distributed scale (use OpenSearch).
- 🔎 **Before:** know your index-size limits.
- 🧭 **After:** copy its developer-first search onboarding.

**PocketBase** — `MIT` · Go/Docker · [source](https://github.com/pocketbase/pocketbase)
- ✅ **Reference when:** you want a single-file backend for a SaaS (auth + DB + realtime + admin in one binary).
- ⛔ **Avoid when:** you need horizontal scale.
- 🔎 **Before:** SQLite limits shape your architecture.
- 🧭 **After:** steal the "backend in one file" DX.

**Forgejo** / **Gitea** — `MIT` · Go · [source](https://codeberg.org/forgejo/forgejo), [source](https://github.com/go-gitea/gitea)
- ✅ **Reference when:** studying a lightweight forge monolith, or the governance story of a community fork.
- ⛔ **Avoid when:** you need GitLab-level CI.
- 🔎 **Before:** understand the Gitea→Forgejo fork split.
- 🧭 **After:** learn from the fork's governance model.

**code-server** — `MIT` · Nodejs/Docker · [source](https://github.com/coder/code-server)
- ✅ **Reference when:** embedding a rich IDE in the browser; study container + auth patterns.
- ⛔ **Avoid when:** you want a light editor.
- 🔎 **Before:** plan resources/permissions.
- 🧭 **After:** copy its "self-hosted dev environment" positioning.

**Appsmith** — `Apache-2.0` · Java/Docker · [source](https://github.com/appsmithorg/appsmith)
- ✅ **Reference when:** building internal-tool/low-code builders; study widget + datasource models.
- ⛔ **Avoid when:** you want a JS-only stack.
- 🔎 **Before:** note open-core boundaries.
- 🧭 **After:** copy the "build CRUD apps 10× faster" pitch.

**Vikunja** — `AGPL-3.0`/`GPL-3.0` · Go · [source](https://github.com/go-vikunja/vikunja)
- ✅ **Reference when:** studying task-management data models with multiple views (list/Kanban/gantt/table).
- ⛔ **Avoid when:** you need heavy team collaboration.
- 🔎 **Before:** understand its API-first design.
- 🧭 **After:** study the multi-view UX.

**Zammad** — `AGPL-3.0` · Ruby · [source](https://github.com/zammad/zammad)
- ✅ **Reference when:** building helpdesk/ticketing; study omnichannel intake + SLA/automation rules.
- ⛔ **Avoid when:** you want a light app.
- 🔎 **Before:** omnichannel integrations add scope.
- 🧭 **After:** copy SLA + automation rules as differentiators.

**Kimai** — `AGPL-3.0` · PHP · [source](https://github.com/kimai/kimai)
- ✅ **Reference when:** building time tracking with reporting and invoicing.
- ⛔ **Avoid when:** you need only a simple timer.
- 🔎 **Before:** project/activity/customer model.
- 🧭 **After:** study its plugin ecosystem.

**Shlink** — `MIT` · PHP/Docker · [source](https://github.com/shlinkio/shlink)
- ✅ **Reference when:** building a URL shortener + analytics + clean REST API.
- ⛔ **Avoid when:** you need deep marketing features.
- 🔎 **Before:** analytics retention/storage.
- 🧭 **After:** copy the CLI + PWA + API trifecta.

**Frigate** — `MIT` · Docker/Python · [source](https://github.com/blakeblackshear/frigate)
- ✅ **Reference when:** building local AI object detection on video; strong edge-AI pipeline reference.
- ⛔ **Avoid when:** you lack GPU/accelerator hardware.
- 🔎 **Before:** hardware acceleration setup.
- 🧭 **After:** study the detected-object event timeline UX.

**BookStack** — `MIT` · PHP/Docker · [source](https://codeberg.org/bookstack/bookstack)
- ✅ **Reference when:** building documentation with a simple book/chapter/page hierarchy.
- ⛔ **Avoid when:** you need real-time co-editing.
- 🔎 **Before:** understand its permission model.
- 🧭 **After:** copy the deliberately simple hierarchy.

**Wiki.js** — `AGPL-3.0` · Nodejs/Docker · [source](https://github.com/Requarks/wiki)
- ✅ **Reference when:** building a modern Node wiki with Git sync and many auth providers.
- ⛔ **Avoid when:** you need a large plugin community.
- 🔎 **Before:** check the v2→v3 migration state.
- 🧭 **After:** study its auth-provider breadth.

---

## 7. Study-first ranking (highest-value references)

Ordered by "how much a TS/React/Convex builder learns per hour":

1. **MedusaJs** — portable headless-commerce architecture in TS.
2. **Payload CMS** — code-first CMS + generated admin, directly transferable.
3. **Rallly** — modern Next.js/Prisma/tRPC product with great onboarding.
4. **Umami** — friendly-license Node analytics; clean data model.
5. **Twenty** — modern TS CRM UX and data modeling.
6. **Documenso** — TS e-signature product end-to-end.
7. **Formbricks** — in-app surveys and targeting patterns.
8. **Langfuse** — LLM observability, the newest high-value category.
9. **Open-WebUI / LibreChat** — multi-provider AI chat UX.
10. **PocketBase** — single-binary backend DX.
11. **Baserow / Mathesar** — friendly UI over structured data.
12. **Plausible / GoatCounter** — minimal, privacy-first product craft.
13. **Listmonk** — high-performance single-binary service.
14. **Zipline** — clean upload/API product.
15. **ntfy / Gotify** — radically simple notification DX.
16. **changedetection.io** — monitoring/watch feature design.
17. **Rocket.Chat / Zulip** — chat product and thread-UX differentiation.
18. **Discourse** — engagement systems (trust levels, badges).
19. **Immich** — mobile-first media backup product.
20. **Home Assistant** — integration-platform architecture.

---

## 8. Reusable checklist: evaluate any app in 5 minutes

1. **Wedge** — What incumbent does it name? Is that market still open?
2. **License** — Can I borrow code, or only ideas? (AGPL ≠ free for a hosted fork.)
3. **Stack reality** — Portable to TS/React/Convex, or inspiration only?
4. **Deploy friction** — One command or five services? (Lower = better reference.)
5. **The `⚠`** — What anti-feature is flagged, and is it core or peripheral?
6. **Health** — Recent releases? Real community? Forked-and-abandoned?
7. **The one thing** — Name the single pattern you'll copy and the single mistake you'll avoid. Then close the tab.
