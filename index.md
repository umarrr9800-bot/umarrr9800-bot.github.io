# Privacy Policy — SpikeX

Last updated: YYYY-MM-DD

1. Overview  
SpikeX (the "App") provides market movement signals and news headlines. This Privacy Policy explains what information the App collects, how it is used, and where data is sent.

2. External endpoints and servers  
- News proxy used by the App (developer‑controlled):  
  https://proxy-news.umar9800-news.workers.dev/fetch-json

  The App issues HTTPS GET requests to this endpoint to fetch news headlines and their publish timestamps. No user credentials or personal identifiers are sent as part of these requests by the App.

3. What the App sends to the proxy server  
- The App sends simple HTTPS GET requests (e.g., with parameter `days=3`) to request recent announcements.  
- Typical request headers (User‑Agent, Accept, etc.) are standard and set by the device/network stack.  
- The App does NOT send email addresses, account identifiers, device identifiers beyond standard headers, or other personal data to the proxy.

4. What the server returns and local caching  
- The server returns JSON objects containing announcement items. Each item typically includes: `id`, `title` (headline), `url`, `publishedTsUtc` (timestamp), and optionally `summary` or translated titles.  
- The App caches fetched announcements locally for a short retention period (typically a few days) to enable offline viewing.

5. Logging on the server  
- The proxy server may log request metadata necessary for operation and abuse control (timestamp, requested path, client IP, response status). IP addresses are logged as part of normal HTTP server logs. Logs should be rotated and retained for a limited time (developer policy).

6. No personal data collected by default  
- The App does not require account creation and does not collect PII (such as name, email, contacts) by default. If the App is later updated to collect such data (e.g., feedback with contact info), the policy will be updated.

7. Notifications & permissions  
- The App may request the POST_NOTIFICATIONS runtime permission (Android 13+) to display alerts for market signals. Users can revoke notification permission in system settings at any time.

8. Third‑party libraries
- The App uses third‑party libraries (Ktor, Jetpack Compose, kotlinx.serialization, etc.) which may perform network operations as part of normal operation.

9. Contact
If you have questions about this Privacy Policy or want to request data deletion, contact: umarrr9800@gmail.com

10. Changes
We may update this policy from time to time. The "Last updated" date will be modified and the updated policy will be published at the same URL.
