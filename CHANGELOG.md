# Changelog

All notable features, updates, fixes, security work, and infrastructure changes for
the awards and grants app are tracked here in reverse chronological order.

This log was reconstructed from the Git history through commit `841dbc3` on
2026-08-12. Merge-only commits are omitted when the underlying feature or fix
commit is listed separately.

## 2026-08-12

### Added

- Added admin controls for duplicating submission questions and review questions,
  including reusable duplication logic and unit coverage for the server actions
  and helper behavior. (`841dbc3`)

## 2026-08-10

### Added

- Added a Neon SSO test flow with login start and callback routes, automatic
  Neon login handling, Neon author synchronization helpers, OAuth transaction
  utilities, and route/unit coverage for the integration. (`093a9ef`)

## 2026-07-29

### Security

- Updated Next.js to pick up the latest security patch available to the app at
  the time. (`c86db74`)

## 2026-07-27

### Changed

- Standardized user-facing and exported submission references around submission
  IDs instead of mutable submission titles across dashboards, reviews, reports,
  accepted decision imports, email flows, payments, and reviewer packets.
  (`bdd6529`)

## 2026-07-24

### Added

- Added user search to the user administration area, including reusable filtering
  utilities and unit coverage. (`89acd87`)

### Changed

- Updated user administration so coauthors are excluded from the main user admin
  list. (`89acd87`)

## 2026-07-08

### Changed

- Aligned the awards report management experience with the related abstracts
  management workflow, including report table actions and admin report behavior.
  (`149f3e8`)

## 2026-07-07

### Added

- Added test submission clearing from submission type administration, including
  the confirmation dialog and server action coverage. (`2768ad5`)

### Fixed

- Fixed admin dashboard submission chart behavior while adding test submission
  cleanup support. (`2768ad5`)

## 2026-07-01

### Added

- Added accepted-as import UI refinements and accepted-as type management
  improvements, with unit coverage for accepted-as actions. (`6a78bd4`)
- Added audience counts to email test sending so admins can see the size of the
  target audience before sending. (`8683202`)
- Added sample merge-field previews to email test sends so admins can validate
  personalized output before sending live audience emails. (`30d0a54`)

## 2026-06-30

### Added

- Added maximum-selection settings for checkbox questions in both submission and
  review forms, including admin configuration, respondent validation, reviewer
  validation, and unit coverage. (`2d6a72c`)
- Added accepted-as reference type administration, including create/edit
  workflows, report/export integration, and email template integration.
  (`40b18e5`)
- Added accepted decision import tooling for admins, including parsing,
  validation, admin UI, actions, and unit coverage. (`749382d`)

### Fixed

- Fixed exported email server helper behavior and covered the template helper
  path with tests. (`d121833`)

## 2026-06-23

### Changed

- Updated submission title copy in the dashboard and submission type picker to
  make the submission-start experience clearer. (`f59d2f5`)

## 2026-06-17

### Added

- Added minimum and maximum repeatable page submission limits, including admin
  page configuration, applicant-side enforcement, finalize-time validation, and
  readonly rendering support. (`45a7747`)

## 2026-06-16

### Security

- Hardened MemberClicks authentication and patched audit dependencies, including
  updated auth route handling, profile helper behavior, and unit tests.
  (`509eebc`)

### Fixed

- Bypassed the Next image optimizer for the home hero image to avoid production
  rendering problems. (`906ea80`)

## 2026-06-15

### Added

- Added per-question word count limits for rich text submission questions,
  including editor character counting, admin configuration, validation, and unit
  tests. (`55f3d87`)

### Security

- Secured auth cookies and tightened admin tenant checks across admin pages,
  dashboard routes, middleware, DAL helpers, redirects, submissions, review
  actions, reports, and payment flows. (`4aaf0db`)

### Fixed

- Handled legacy zero page group answers in readonly submission rendering.
  (`ee1318a`)

## 2026-06-12

### Added

- Added the first full draft of multi-submit pages, allowing repeatable page
  groups for submissions with applicant entry management, reporting support,
  review packet support, readonly rendering, S3 handling, and unit coverage.
  (`c0625b2`)

### Changed

- Applied schema updates needed for the evolving submission/page data model.
  (`1e64a13`)
- Removed the Coolify deployment workflow from the repository. (`53bbd84`)

### Fixed

- Fixed multi-submit page behavior around page group transactions, finalization,
  readonly displays, and editor interactions. (`52cdbb4`)

## 2026-06-11

### Added

- Added public submission links to report exports and committee-facing routes,
  with helper coverage for URL generation. (`79aca76`)

## 2026-06-10

### Changed

- Preferred abstract/submission titles in report submission displays where a
  human-readable title is still appropriate. (`6c05cd0`)
- Scoped submission answers to the applicant/author context to avoid mixing
  answers across authors or page groups. (`b6e87fe`)

### Fixed

- Fixed public client logo rendering on the landing page. (`6687c30`)
- Added sanitized database URL logging to the instance route to support safer
  operational debugging. (`64c25f3`)

## 2026-05-29

### Added

- Added service offline mode with middleware routing and coverage. (`c0fc270`)
- Expanded committee score output to include richer answer details and missing
  reviewer responses. (`dbc6e28`, `7e9a06b`)

## 2026-05-28

### Added

- Added committee score links for direct access to committee scoring views.
  (`eb3ddbd`)

## 2026-05-27

### Changed

- Allowed submissions to be finalized when remaining unanswered pages contain
  only optional questions. (`45e4196`)

### Fixed

- Added optional-page badges so unanswered optional-only pages are represented
  accurately in the submission workflow. (`5851710`)

## 2026-05-20

### Changed

- Updated outbound mail integration to use `ccEmail` and `bccEmail` payload
  fields for CC/BCC delivery. (`045792a`)

## 2026-05-19

### Added

- Added member-specific payment settings for submission types so payment rules
  can vary by member context. (`17330f5`)
- Allowed admins to preview invite-only rounds without requiring an active user
  invite. (`17b03e3`)

### Changed

- Removed the `n=` query parameter from report export URLs. (`1457290`)

## 2026-05-15

### Changed

- Updated report export links to derive their origin from the browser context.
  (`6c1a054`)

## 2026-05-14

### Added

- Added a reviewer completion admin table for tracking reviewer progress.
  (`b0e1292`)

### Changed

- Updated reviewer admin ordering and report export behavior. (`db4aa01`)
- Aligned the payment transaction schema with the database. (`96d47b0`)
- Refined payment return and redirect origin handling to use browser and public
  origins consistently. (`f3647cb`, `b7c313f`, `571d4e5`)

## 2026-05-13

### Added

- Added a static Collect Checkout payment flow for paid submissions. (`dd148aa`)

### Fixed

- Fixed payment context server action exports. (`717c486`)
- Avoided false canceled-payment banners after successful or neutral payment
  returns. (`915788a`)
- Fixed host/origin resolution when returning from payment. (`9533ca5`,
  `a48094b`)

## 2026-05-11

### Added

- Added rich text support to email templates. (`fc1a48c`)
- Added CC and BCC support for audience emails. (`2e84f17`)

## 2026-05-08

### Added

- Added assignment algorithm preview tooling for admins, including submission
  type scoping and a publish action for applying generated assignments.
  (`5340654`, `85c1816`, `d52a0a9`)
- Added an optional review conflict question to support reviewer conflict
  disclosures. (`0916f25`)

## 2026-05-06

### Added

- Added reviewer filtering by submission type and reviewer assignment visibility
  by submission type in the reviewer administration workflow. (`baa0278`,
  `d923bcf`)

## 2026-05-05

### Changed

- Removed submitted timestamps from confirmation emails. (`081d80c`)

## 2026-04-27

### Added

- Added dynamic reviewer guidelines. (`b5b53e5`)
- Added reviewer assignment counts for admin assignment visibility. (`0273fd1`)

## 2026-04-24

### Added

- Added reviewer counts to the report builder. (`21c579e`)
- Added Coolify auto-deploy configuration. (`d9a684f`)

### Changed

- Cleaned report builder review output and refined score averages. (`8ca90af`,
  `1b9e7d4`)

## 2026-04-23

### Changed

- Simplified and refined review packet PDF content and layout, trimmed extra PDF
  text, and renamed the review packet button for clearer reviewer use.
  (`8ace8b2`, `480c63a`, `eb4905e`, `fff41c9`)

## 2026-04-22

### Added

- Added review-side submission question filtering so review packets and review
  pages can hide or show submission answers based on configured review needs.
  (`620de0f`)
- Added submission type filtering to reviewer assignments. (`776904c`)

## 2026-04-21

### Added

- Added PDF-only review-side submission exports for reviewer packets. (`7f3f0ef`)
- Added a review form scroll shortcut for faster reviewer navigation.
  (`9fc9848`)

## 2026-04-19

### Fixed

- Filtered readonly submission branches so conditional or branched answers render
  correctly in admin, reviewer, and applicant views. (`3229688`)

## 2026-04-17

### Changed

- Normalized line endings in the MemberClicks authentication helper. (`b9c8917`)

## 2026-04-16

### Added

- Added per-instance email sender configuration for outgoing mail. (`ec7c7d4`)

### Changed

- Increased the server action upload size limit for larger submission payloads or
  files. (`7db8ecb`)

## 2026-04-13

### Added

- Added tracking for CollectCheckout submission transactions in the database and
  finalization flow. (`cd7735c`)

### Changed

- Updated instance lookups so only active instances are eligible for public
  instance resolution. (`e077cc7`)

## 2026-04-09

### Added

- Added rich text subheadings to review questions. (`b6e325f`)
- Added heading-only review questions for non-scored/instructional review form
  sections. (`f4bd9e0`)

## 2026-04-06

### Added

- Added the initial internal API route for member intelligence activity.
  (`2a5ffc0`)

## 2026-04-02

### Added

- Added rich text support to submission question subheadings across admin
  configuration, applicant forms, review pages, reports, readonly submission
  sections, and finalize handling. (`3a8db10`)

### Fixed

- Fixed bullet list rendering in rich text subheadings. (`8af8cf7`)

## 2026-04-01

### Added

- Added an email field type flag option for submission questions, including admin
  setup, applicant validation, rendering, and unit coverage. (`d89fb4b`)

## 2026-03-31

### Added

- Added paid submission functionality with submission type payment settings,
  finalize-time payment handling, success/cancel routes, and payment button UI.
  (`2c70e27`)

### Changed

- Moved the coauthor management box below the submission steps. (`7c5f633`)

### Fixed

- Removed a duplicate ending from confirmation emails. (`957486f`)

## 2026-03-27

### Added

- Added dynamic sidebar guideline links for submissions, including navigation
  helper coverage. (`05ff091`)

## 2026-03-26

### Fixed

- Hid invited submissions when the user no longer has active invites. (`15026d3`)

## 2026-03-24

### Added

- Added configurable coauthor fields per submission type, including admin
  toggles, applicant coauthor management, label helpers, and unit coverage.
  (`9b4869b`)

### Changed

- Removed legacy award author role usage from admin, email, user administration,
  coauthor, and shared type code. (`e0bc0cb`)

## 2026-03-23

### Added

- Added the first draft of the coauthor system, including submission type
  controls, applicant coauthor actions, manager UI, and tests. (`be7642f`)

## 2026-03-20

### Changed

- Tested instance resolution by submission URL host, then reverted the approach
  to restore the prior instance route and landing-page behavior. (`f72310b`,
  `616686d`)

## 2026-03-17

### Changed

- Updated round two labels in submission type dialogs. (`a39fce7`)
- Simplified submission type audience labels in admin tables. (`42b8c1b`)

## 2026-03-16

### Changed

- Updated login and logout flows to use `sso_domain`, including related
  MemberClicks login parameters and instance schema fields. (`0f243f5`,
  `1426297`)

## 2026-03-13

### Added

- Added round two workflows on both admin and user sides, including round
  invites, invite controls, invited submission cards, review visibility,
  submission finalization changes, and review assignment support. (`c8b2acb`)
- Added submission type audience gating so submission types can be limited to
  members or opened to all eligible users. (`e0fce46`)

## 2026-03-12

### Added

- Added unit coverage for report helpers, cookie utilities, editor URLs, email
  templates, field type helpers, S3 helpers, and report metadata. (`5e3441a`)

### Changed

- Removed unassigned submission types from reports. (`cb01cb1`)
- Redirected logout to the app landing page. (`894ed9d`)

## 2026-03-09

### Added

- Added user administration with instance role editing. (`2275106`)
- Added a volunteer role that bypasses submission windows where appropriate.
  (`ae6f052`)
- Added an external Create Account button on the landing page. (`4ddaa3d`)

### Fixed

- Fixed submission question reorder cache revalidation. (`909c155`)
- Fixed drag-and-drop reorder state persistence for submission and review
  questions. (`c22fcb0`)

## 2026-03-07

### Changed

- Allowed admins to test submission forms outside open submission windows using
  the real admin test forms. (`dafaf24`)
- Removed legacy preview routes in favor of the real admin test flow.
  (`5eb7037`)
- Updated login button labels to say "Log In". (`1fb08b7`)

## 2026-03-05

### Added

- Added timezone-aware submission windows with exact open and close times,
  submission type admin controls, dashboard visibility handling, and unit
  coverage. (`532ee2e`)
- Added review open/close scheduling and enforcement in review pages, review
  actions, and admin review question management. (`0498616`)

## 2026-03-04

### Added

- Added guideline URLs to submission types and moved guideline links onto
  submission type cards. (`c831dbd`, `1e01fc7`)

### Changed

- Updated submission type guideline links to use CloudFront URLs. (`8a07b11`)

## 2026-03-03

### Added

- Added guideline file handling and CloudFront URL support in dashboard cookie
  utilities, guidelines pages, and layout. (`f9dfe71`, `5c66604`)

### Changed

- Updated submission open/close handling. (`bbea9c8`)
- Restricted upload fields to DOCX and PDF files. (`5c0d037`)

## 2026-03-02

### Added

- Populated landing page text from the database instance record and included
  `login_page_text` in the instance cookie. (`2f06b92`, `028c601`)

### Changed

- Updated page metadata, display polish, landing page text width, and initial
  submission listing order. (`52dda35`, `5521236`, `35e756c`, `d85a96f`)

## 2026-02-26

### Changed

- Updated the step/page submission flow. (`b306b57`)
- Moved the United States to the top of country dropdowns. (`e51b703`)

## 2026-02-24

### Added

- Added initial unit tests for the then-current behavior. (`4632238`)

### Fixed

- Applied bug fixes after the February field and rendering changes. (`8a192db`)

## 2026-02-23

### Added

- Added a heading field type option for non-answer/instructional submission
  fields. (`e281642`)

### Changed

- Tweaked question rendering information. (`3a2e11a`)

### Fixed

- Fixed a bug where a step showed as complete when no questions on the step were
  required. (`beb7f59`)

## 2026-02-20

### Added

- Added "Other" field support for selectable answers. (`291a21a`)
- Added country and state dropdown field support, then updated options to show
  full names instead of abbreviations. (`dfa419e`, `6c48de2`)
- Added admin-controlled question show/hide logic. (`dc3c569`)

### Changed

- Removed visible ordinals from questions to keep show/hide behavior consistent.
  (`fb32377`)

## 2026-02-13

### Fixed

- Fixed linting errors across the app. (`dba3a9c`)

## 2025-12-05

### Changed

- Updated the Next.js version used by the app. (`41560ce`)

## 2025-11-10

### Changed

- Cleaned up Prisma generation and schema configuration by removing the shadow
  database setting, moving generated client output out of the local directory,
  updating Prisma client generation options, and downgrading the Prisma client
  for compatibility. (`96db492`, `263dfc8`, `18c468e`, `1d1e605`)

## 2025-11-08

### Added

- Added the rich text editor to submission and review form experiences.
  (`4aa7ea7`)

## 2025-11-04

### Added

- Added reusable rich text editor components. (`8b712f2`)

## 2025-10-27

### Added

- Completed admin dashboard chart work after adding additional charts.
  (`bea8345`, `3a8d0ad`)

### Fixed

- Resolved TypeScript errors from the chart/admin dashboard work. (`acade96`)

## 2025-10-26

### Added

- Added shadcn chart support, reorganized admin navigation, and introduced the
  initial dashboard charts. (`572c96f`, `d2fad14`)
- Added working default email template support. (`cc92acc`)

## 2025-10-25

### Added

- Completed test email and regular audience email sending. (`3f07543`)

## 2025-10-24

### Added

- Added the initial email administration section. (`b137502`)
- Added the email creation form. (`60ef973`)
- Hooked up test email sending. (`b6cb4fb`)

### Changed

- Added sidebar hover states and visual pills to admin navigation. (`9d95dae`)

## 2025-10-22

### Added

- Added numerical scoring and average calculations to reporting. (`6878be7`)

## 2025-10-21

### Changed

- Reworked the initial reports area into a report builder. (`2d0e16e`)
- Removed breadcrumbs from the navigation experience. (`92de705`)

## 2025-10-20

### Added

- Added the initial reports section, report data table buildout, and report table
  actions for view, edit, and unsubmit. (`827e92e`, `bb54d0f`, `47e199d`)

### Changed

- Clarified navigation options. (`7f139c9`)

## 2025-10-17

### Changed

- Moved reviews out of a collapsible dashboard area and into a dedicated page.
  (`6a22ebc`)

## 2025-10-16

### Added

- Added custom review questions, reviewer assignment, rendered review questions,
  and the completed review submission flow. (`58d2698`, `f89a0e1`)

## 2025-10-15

### Added

- Added a review guidelines page. (`1345fcf`)

### Changed

- Applied minor text updates across the system. (`1345fcf`)

## 2025-10-10

### Added

- Added submission naming. (`a48422d`)

### Changed

- Gated review navigation/options by user roles. (`c350ca7`)
- Updated base64 encoding in the logout route. (`57f0d01`)

### Fixed

- Fixed a build error after early app integration work. (`5ded2f7`)

## 2025-10-09

### Added

- Added instance-specific styling. (`21c2e8f`)
- Added file upload questions backed by S3 storage. (`3ed9333`)
- Added final submission confirmation emails using SES. (`d9a9cfa`)

### Fixed

- Fixed logout issues and refined the logout flow. (`6529acc`, `fe5ef04`)

### Removed

- Deleted the legacy Award PRD file from the repository. (`bcd808c`)

## 2025-10-08

### Added

- Added edit, final submit, and submitted-view behavior for submissions.
  (`a2b1512`)

## 2025-10-07

### Added

- Added initial dynamic question rendering for paragraph and single-line fields.
  (`84d7364`)
- Added checkbox, radio, and dropdown rendering for submission questions.
  (`421af01`)
- Completed the initial homepage design. (`f6d28da`)

## 2025-10-06

### Added

- Added admin breadcrumb navigation. (`5f2368e`)

## 2025-10-03

### Added

- Added dynamic submission type pages and question stubs after selecting a
  submission type. (`12bd76d`)
- Added immediate creation of new submissions in the award table to support
  future editing and display submissions in the applicant list. (`0f37180`)
- Added instance-specific logo display. (`7df87af`)

### Changed

- Updated custom logo rendering to use Next Image and allow CloudFront-hosted
  images in configuration. (`585a79f`)

## 2025-10-02

### Changed

- Reimagined administration around a submission type to pages to questions
  hierarchy, replacing the earlier award-type/award-question organization.
  (`568b9d3`)

## 2025-09-18

### Added

- Added award types and award questions administration sections. (`97f12f7`)

## 2025-09-12

### Added

- Added the dashboard sidebar, admin DAL, and the first sidebar option model.
  (`57c6fcd`)

## 2025-06-23

### Added

- Implemented the MemberClicks login flow. (`bd99f72`)

## 2025-06-20

### Added

- Added the initial local Next.js, Prisma, and development environment setup.
  (`6b9e6d2`)

### Changed

- Merged remote repository content into the local setup and removed obsolete
  architecture/task files. (`293d56d`, `a3420c4`)

## 2025-06-18

### Added

- Created the initial repository. (`28f366c`)
