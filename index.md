# Signal Trace App Privacy Policy

**Effective date:** 29 September 2026  
**Last updated:** 29 September 2026

## 1. Scope

This App Privacy Policy applies to the Signal Trace Android application ("Signal Trace", "app", "we", "us", or "our").

Signal Trace is currently designed as a local-first creative learning and app-marketing analysis workspace. The app can connect to external services selected by the user, process creative media locally, correlate time-based marketing and store signals, and optionally synchronize a scoped Companion device with a Workspace.

This Policy covers the Signal Trace app itself. It does not by itself govern the public website at materialize-thoughts.com, which is covered separately by the Materialize Thoughts website privacy policy.

## 2. Controller and Contact

The controller for personal data processed by Materialize Thoughts in connection with Signal Trace is:

Pascal Schönfeld  
Materialize Thoughts  
Marrensberg 9  
24944 Flensburg  
Germany  
materialize.thoughts@gmail.com

For data that remains exclusively inside a user's local Workspace, or for third-party data a Workspace operator chooses to import or connect, the Workspace operator may independently be responsible for determining the lawful basis and purposes of that processing under applicable law.

## 3. What Signal Trace Is

Signal Trace is designed to help app developers and small app-growth teams understand their creative marketing workflow without claiming deterministic user-level attribution where only temporal evidence exists.

Depending on the features you use, Signal Trace can:

- organize Content Pieces, Creatives, Variations, Publications, ideas, tasks, hypotheses, and learnings;
- connect to supported Publication Sources and Connectors such as TikTok, Google Play, Google Ads, and configured custom REST/JSON sources;
- store time-series observations and show them together on a Timeline;
- detect and analyze creative media locally, including frame extraction, optical character recognition (OCR), text embeddings, visual embeddings, and classification;
- learn a Workspace-specific creative vocabulary from classifications that the user reviews or corrects;
- generate user-initiated AI Handoff packages containing selected context and evidence;
- pair a Workspace with scoped Companion devices for creators or for the Workspace operator's own mobile use; and
- optionally send local notification emails through an SMTP service configured by the user.

## 4. Local-First Privacy Approach

Signal Trace is designed around a local-first architecture.

The current product does **not** require a hosted Signal Trace account service, hosted Signal Trace analytics database, or hosted Signal Trace AI-analysis backend for its core operation. The canonical analytical store is local SQLite storage on the device. On Android, connector credentials and other sensitive secrets are stored through a secure credential abstraction backed by Android Keystore-encrypted storage; the local database stores opaque secret references rather than plaintext secrets where that architecture applies.

Signal Trace does not need to upload the user's complete Workspace to a Materialize Thoughts analysis cloud in order to provide its core analysis features.

This does **not** mean that no network communication ever occurs. Network communication is necessary when the user configures external connectors, downloads local AI model files, uses a user-configured SMTP provider, pairs or syncs devices over a network transport, or intentionally exports data to another service.

## 5. Categories of Data Processed

Depending on how Signal Trace is configured and used, the app may process the following categories of data.

### 5.1 Workspace content created by the user

This may include:

- app or project names;
- Content Pieces and Creative records;
- ideas and inspiration references;
- Variations and experiment relationships;
- publication plans and publication links;
- notes, labels, tags, topics, hooks, angles, messages, calls to action, formats, visual-style labels, and other taxonomy values;
- hypotheses, learnings, tasks, reminders, and review decisions;
- manually entered context and source information; and
- local settings and preferences.

### 5.2 Publication Source data

When the user connects a supported Publication Source, Signal Trace may retrieve and locally store data made available through that source or necessary to understand Publications.

For TikTok, this can include, depending on the available API or public-source response:

- connected-account identifiers and account metadata;
- OAuth access and refresh information stored securely on the device;
- video or Publication identifiers;
- publication time;
- validated Publication URLs;
- captions and available source metadata;
- cumulative and interval-derived engagement observations such as views, likes, comments, shares, and saves where available;
- music or sound metadata where exposed by the source;
- media or media references used for local creative analysis; and
- public comments and replies for eligible owned Publications when the user invokes or enables that functionality.

For stored public TikTok comments, Signal Trace is designed not to persist platform usernames, display names, avatars, profile URLs, bios, or raw cross-post author identifiers. Author and comment identifiers may be processed transiently during synchronization and converted before persistence into deterministic pseudonymous identifiers scoped to the individual Publication, so that Signal Trace does not build a cross-post participant profile from those identifiers.

### 5.3 Google Play data

If the user configures the Google Play integration, Signal Trace may process locally:

- service-account or other connector credentials required by the configured integration;
- app/package identifiers and report configuration;
- store listing visitor observations;
- install and acquisition observations;
- supported store-performance and time-series report data; and
- connector synchronization and coverage metadata.

The exact data available depends on the reports and permissions exposed by the user's Google Play / Google Cloud configuration.

### 5.4 Google Ads data

If the user configures Google Ads, Signal Trace may process locally:

- OAuth tokens and related connector credentials;
- customer and campaign identifiers;
- campaign names;
- status and delivery observations;
- impressions;
- clicks;
- cost information;
- conversion metrics; and
- daily or hourly reporting data where supported and configured.

### 5.5 Custom REST / JSON connector data

Signal Trace includes an evolving custom connector architecture. Where the user configures a custom REST/JSON source, the app may process the endpoint configuration, required authentication material, event names, timestamps, counts, or other configured time-series fields returned by that source.

The user is responsible for ensuring that a custom endpoint is lawful to connect to and that the user is authorized to process the data returned by it.

### 5.6 Creative media and local analysis evidence

When Creative Understanding / classification features are used, Signal Trace may process locally:

- images, carousel slides, video media or cached media needed for analysis;
- selected or extracted video frames;
- scene-change information;
- visible text detected by OCR;
- OCR confidence and bounding-box information;
- normalized text;
- text embeddings;
- visual embeddings;
- classification suggestions and confidence information;
- user-reviewed or user-corrected classifications; and
- technical analysis evidence needed to explain or reproduce the local classification result.

The current classification pipeline is designed to run locally rather than through a hosted Signal Trace AI service.

### 5.7 Workspace vocabulary and reviewed classifications

Signal Trace can adapt to the terminology of a Workspace. User-confirmed or corrected classifications may be retained locally as example knowledge so that future suggestions better match the Workspace's own vocabulary and creative taxonomy.

### 5.8 Companion device data

If Workspace/Companion functionality is used, Signal Trace may process:

- Workspace and Device identifiers;
- Device labels and roles;
- public cryptographic keys;
- encrypted or securely referenced private key material;
- per-device synchronization keys;
- pairing invitations and expiry state;
- assigned Account / Creative Source scope;
- permissions;
- authority revisions;
- task and reminder state;
- scoped Content Pieces, Creatives, Publications, ideas, Variations, learnings, and observations required by the assigned permissions; and
- synchronization metadata needed for ordering, replay protection, acknowledgement, revocation, and recovery.

A Companion is intended to receive only the Workspace scope assigned to that Device.

### 5.9 QR pairing and camera use

Where QR pairing is used, the Companion may access the device camera to scan a Signal Trace pairing QR code. QR decoding is performed locally by the app. The camera image is not intended to be uploaded to Materialize Thoughts for QR recognition.

The QR itself contains a short-lived local-network transfer reference rather than the complete Workspace data package. The actual pairing package remains encrypted and signed.

### 5.10 Notification and SMTP configuration

If the user enables email notifications, Signal Trace may process locally:

- notification email address;
- SMTP host and port;
- SMTP security mode;
- SMTP username;
- sender address;
- securely stored SMTP password or secret reference; and
- the notification content selected for delivery.

Email is sent through the SMTP infrastructure configured by the user rather than through a hosted Signal Trace notification backend.

### 5.11 Support and feedback

If the user contacts us or voluntarily sends support material, we may process:

- email address and correspondence;
- screenshots or files the user chooses to send;
- diagnostic exports or logs the user chooses to provide;
- app version, Android version, device information, and technical error context relevant to the request; and
- other information the user deliberately includes in the support request.

## 6. Purposes of Processing

Where applicable, personal data is processed for purposes including:

- providing the user's local Signal Trace Workspace;
- connecting to external services selected by the user;
- collecting and reconciling source observations;
- organizing Publications, Creatives, Variations, ideas, tasks, hypotheses, and learnings;
- displaying Timeline and comparison views;
- performing local OCR, embedding, classification, and Creative Understanding;
- improving Workspace-specific classification suggestions from user-reviewed examples;
- generating user-requested AI Handoff exports;
- securely pairing, authorizing, synchronizing, and revoking Companion devices;
- sending notifications through a user-configured transport;
- maintaining security, integrity, recovery, and connector health;
- troubleshooting user-requested support issues; and
- complying with legal obligations and protecting our rights.

We do not sell personal data.

## 7. Legal Bases

Where EU, EEA, UK, or similar data-protection law applies and Materialize Thoughts acts as controller, processing may rely on one or more of the following legal bases depending on the context:

- performance of a contract or steps taken at the user's request before entering into a contract;
- legitimate interests in providing, securing, maintaining, and supporting Signal Trace;
- compliance with legal obligations; and
- consent, where consent is required.

Signal Trace can also be used by a Workspace operator to process data relating to creators, commenters, customers, or other third parties. In those situations, the Workspace operator is responsible for determining whether it has an appropriate legal basis and for meeting any transparency or other obligations that apply to its own use of that data.

## 8. Local Storage and Retention

Core Workspace data is primarily stored locally on the device in the app's local database and app-private files.

Local data may remain until:

- the user edits or deletes it;
- the user removes a Publication, Creative, Workspace item, connector, or Companion relationship;
- the app's retention or reconciliation rules remove temporary analysis/cache material;
- the user clears app storage;
- the user uninstalls the app; or
- the device or operating system removes application data.

Some historical observations are intentionally retained because the product is designed to compare changes over time. Connector-health and synchronization metadata may also remain locally as needed to preserve data integrity, coverage information, replay protection, or revocation state.

Support communications or materials sent directly to us are retained only as long as reasonably necessary for support, security, documentation, legal compliance, or related operational purposes.

## 9. Connector Credentials and Secrets

Connector credentials may include OAuth tokens, service-account material, API credentials, SMTP credentials, pairing secrets, synchronization keys, or other authentication information entered or generated for a configured feature.

On Android, Signal Trace is designed to keep sensitive connector and cryptographic secrets behind a secure credential abstraction backed by Android Keystore-encrypted storage. Where applicable, SQLite stores only an opaque reference to the secret.

Secrets required by an authorized Companion may be transferred only within that Device's assigned scope through the encrypted and signed pairing/synchronization protocol.

Users remain responsible for securing their device, Google/TikTok accounts, connected services, local backups, unlock credentials, and any external file-transfer channel they choose to use.

## 10. External Services and Network Communication

Signal Trace communicates with external services only when required by a feature the user configures or invokes. Depending on configuration, recipients may include:

- TikTok services and APIs;
- Google Play / Google Cloud services used by the configured Play reports;
- Google Ads APIs;
- a custom REST/JSON service configured by the user;
- an SMTP provider configured by the user;
- model-file hosting used to download local AI/OCR model files; and
- an external AI provider chosen by the user after the user exports an AI Handoff package.

Those providers process data under their own terms and privacy notices where they act independently.

## 11. TikTok Connection

TikTok connectivity may use OAuth and TikTok APIs to access data authorized by the user. Signal Trace may also access eligible public TikTok resources required for product features such as publication references, media understanding, or public comments for owned Publications.

Signal Trace is designed to fail closed when TikTok requires interactive login, CAPTCHA, device verification, or otherwise blocks the requested public access. It is not designed to bypass such controls.

The user's TikTok credentials or tokens are used only for the configured Signal Trace integration and are stored locally through the app's credential architecture.

## 12. Google Play and Google Ads Connections

Google Play and Google Ads integrations communicate directly from the local Signal Trace runtime to the relevant Google services using credentials configured by the user.

Google may receive the technical information ordinarily associated with such API requests and will process data under Google's own applicable terms and privacy documentation.

Signal Trace stores the resulting configured marketing/store observations locally for Timeline, comparison, and Store Response analysis.

## 13. Local AI Models and Model Downloads

Signal Trace's Creative Understanding features use local model files for tasks such as OCR, text embeddings, and visual embeddings.

Required model artifacts may be downloaded from third-party model hosting, currently including resources hosted through Hugging Face. A model-hosting provider may receive ordinary technical request information such as IP address, request time, user agent or similar delivery metadata when the model file is downloaded.

Workspace content, Creative text, images, OCR results, embeddings, and classification evidence are not intended to be sent to the model-hosting provider merely because a model binary is downloaded.

## 14. AI Handoff Exports

AI Handoff is user-initiated.

Signal Trace can assemble a structured package from the explicit scope selected by the user, for example a Timeline range, Publication, Content Piece, Variation comparison, Idea, or other supported context. Depending on that scope, the export may contain Creative media evidence, OCR text, classifications, metrics, Distribution observations, Store Response context, learnings, hypotheses, and explanatory metadata.

Signal Trace does not automatically upload that package to ChatGPT, Claude, or another external AI provider as part of the Handoff generation itself. The user decides whether, where, and to whom the resulting package is transferred.

If the user uploads the package to an external AI provider, that provider's privacy policy, terms, retention rules, and account settings apply to the uploaded content. Users should review the package and avoid exporting information they are not authorized to disclose.

## 15. Companion Pairing and Synchronization

Signal Trace's Companion architecture is designed without a hosted Signal Trace synchronization account.

Pairing and synchronization use versioned encrypted and signed packages. Current pairing uses cryptographic Device and Workspace identities, per-device synchronization keys, scoped permissions, and revocation state. Local QR pairing transfers the canonical encrypted pairing package over the user's reachable private LAN. File-based pairing and synchronization packages may also be transferred through an external channel chosen by the user.

If the user chooses an external transfer channel such as email, messaging, cloud storage, or another file-sharing service, that third-party service may process the encrypted file and associated delivery metadata under its own privacy terms.

A Companion is intended to receive only its assigned scope. Revoking a Device prevents future authorized synchronization and causes scoped state to be reconciled according to the app's revocation rules.

## 16. Public Comments and Other People's Data

Some Signal Trace features can process public content or data that relates to people other than the Workspace operator, for example public TikTok comments or Creative work submitted by an invited creator.

Signal Trace is a tool used under the control of the Workspace operator. The Workspace operator is responsible for using these features lawfully, limiting access appropriately, and complying with any notice, retention, employment, contractor, intellectual-property, or data-protection obligations that apply to its own activities.

Because the product is local-first, Materialize Thoughts normally does not receive the underlying Workspace content merely because the user stores or analyzes it in Signal Trace.

## 17. When Data May Leave the Device

Data may leave the device in situations including:

- when Signal Trace communicates with a Publication Source or Connector explicitly configured by the user;
- when the app downloads required model files or other user-requested resources;
- when a Workspace and Companion exchange an encrypted pairing or synchronization package over a configured transport;
- when the user transfers an encrypted `.stpair` or `.stsync` file through an external channel;
- when the user enables SMTP email notifications;
- when the user creates and then intentionally shares an AI Handoff package;
- when the user contacts us or voluntarily provides diagnostic/support material; or
- when disclosure is required by law.

Core Workspace analysis is not designed around continuous upload to a Materialize Thoughts cloud service.

## 18. Sharing and Recipients

We do not share Signal Trace Workspace data with third parties for their own advertising purposes.

Where Materialize Thoughts itself receives or discloses personal data, recipients may include:

- service providers used for communications, support, website/app distribution, or other operational purposes;
- platform providers involved in app distribution;
- professional advisers where reasonably necessary;
- legal, regulatory, judicial, or public authorities where required by law; and
- successors or counterparties in a merger, acquisition, restructuring, or similar transaction, subject to applicable law.

External services configured directly by the user, such as TikTok, Google, SMTP, custom REST services, file-transfer providers, or external AI providers, may independently process data under their own terms when the user activates those workflows.

## 19. International Transfers

External services selected or configured by the user may process data in countries outside the user's country, the European Economic Area, or the United Kingdom.

Where Materialize Thoughts transfers personal data internationally and applicable law requires safeguards, we rely on an adequacy decision, standard contractual clauses, or another valid transfer mechanism as appropriate.

Transfers initiated directly by the user to independently selected external services are also subject to the terms and transfer mechanisms of those providers.

## 20. Security

Signal Trace is designed to use reasonable technical safeguards appropriate to its local-first architecture, including local database boundaries, app-private storage, secure credential storage, encrypted pairing/synchronization payloads, signatures, scoped Device permissions, replay/idempotency controls, and Device revocation mechanisms.

No electronic storage, network transport, cryptographic system, device, or external provider can be guaranteed to be completely secure. Users are responsible for protecting device access, operating-system credentials, connected accounts, backups, exported files, pairing codes, and any external services they choose to use.

## 21. App Permissions and Background Operation

Depending on Android version and features used, Signal Trace may request or use permissions or capabilities including:

- Internet access for configured connectors and resource downloads;
- network-state access to schedule or perform network-dependent synchronization;
- notifications for local reminders or connector-attention alerts;
- boot-completion handling so scheduled local background work can be restored after device restart; and
- camera access when the user chooses QR-based Companion pairing.

Background connector refresh uses Android scheduling. Android may delay scheduled work because of operating-system power or background-execution policies.

## 22. Automated Analysis and Human Review

Signal Trace can generate automated classification suggestions and modeled analytical context. These results are intended to support human review and creative learning.

Signal Trace is specifically designed not to convert temporal correlation into a deterministic claim that a particular Creative caused a particular install or user action where the underlying evidence does not support that conclusion.

Users remain responsible for reviewing classifications, comparisons, hypotheses, learnings, and business decisions.

## 23. Your Rights

Depending on your jurisdiction, you may have rights including:

- access to personal data;
- rectification of inaccurate data;
- erasure;
- restriction of processing;
- objection to processing;
- data portability;
- withdrawal of consent where processing is based on consent; and
- the right to lodge a complaint with a competent supervisory authority.

Because Signal Trace is primarily local-first and does not require a general Signal Trace cloud account for core use, some rights may need to be exercised directly on the device where the relevant data exists only locally and has never been received by Materialize Thoughts.

For privacy-related requests concerning data actually held by Materialize Thoughts, contact materialize.thoughts@gmail.com.

## 24. Children

Signal Trace is a professional creative-marketing and app-growth tool and is not directed to children under the minimum age required by applicable law in their jurisdiction.

We do not knowingly seek to collect personal data from children through Signal Trace. If you believe a child has provided personal data to Materialize Thoughts inappropriately, contact us.

## 25. Changes to this Policy

Signal Trace is under active development. Integrations, Companion capabilities, local-analysis functionality, and distribution methods may evolve.

We may update this App Privacy Policy when product behavior or legal requirements change. The updated version will carry a new effective or last-updated date and may also be referenced from the app, the Materialize Thoughts website, the app-store listing, or another appropriate channel.

## 26. Contact

For privacy-related questions, requests, or complaints:

Pascal Schönfeld  
Materialize Thoughts  
Marrensberg 9  
24944 Flensburg  
Germany  
materialize.thoughts@gmail.com
