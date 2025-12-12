# Privacy Policy — CryptoPump

Last updated: YYYY-MM-DD

1. Overview  
CryptoPump (the "App") provides market movement signals and news headlines. This Privacy Policy explains what information the App collects, how it is used, and where data is sent.

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
``` ````

Далее — два варианта размещения. Выберите тот, что удобнее.

Вариант A — Рекомендуемый (простой): опубликовать как пользовательскую страницу (username.github.io)
- Плюсы: URL будет простой и постоянный: https://<your-github-username>.github.io/  
- Минусы: нужно создать репозиторий с именем username.github.io

Шаги (веб UI — самый простой способ)
1. Войдите в GitHub под вашим аккаунтом (https://github.com).
2. Нажмите правый верхний «+» → New repository.
3. В поле Repository name введите: <ВАШЕ_ИМЯ_ПОЛЬЗОВАТЕЛЯ>.github.io  
   Пример: umarrr9800.github.io
4. Сделайте репозиторий Public (обязательно для Pages) и нажмите Create repository.
5. После создания репозитория в веб‑интерфейсе нажмите Add file → Create new file.
6. В поле "Name your file..." введите index.md (если хотите, чтобы корень сайта служил вашей страницей) или privacy_policy.md (в этом случае URL будет https://username.github.io/privacy_policy.html). Рекомендую index.md, чтобы URL был просто https://username.github.io/.
7. Вставьте содержимое privacy_policy.md (из блока выше) в редактор.
8. Пролистайте вниз, в поле Commit new file введите сообщение (например "Add privacy policy") и Commit new file.
9. GitHub Pages для репозитория username.github.io будет автоматически опубликована; подождите 1–2 минуты.
10. Откройте https://<username>.github.io/ — вы должны увидеть вашу страницу в HTML (GitHub Pages рендерит Markdown).

Шаги (CLI git)
Если вам удобнее с терминалом:

- Создать локальный репозиторий и запушить:
```bash
cd ~/projects
mkdir privacy-site
cd privacy-site
git init
echo "# Privacy Policy" > index.md
# либо вставьте готовый privacy_policy.md в index.md
git add index.md
git commit -m "Add privacy policy"
# создайте удалённый репозиторий с именем username.github.io на GitHub (через UI) и добавьте remote
git remote add origin git@github.com:YOUR_USERNAME/YOUR_USERNAME.github.io.git
git branch -M main
git push -u origin main
```
- Подождите несколько минут, откройте https://YOUR_USERNAME.github.io/

Вариант B — Project Pages (репозиторий проекта)
- Создаёте обычный репозиторий, кладёте файл в папку /docs или в корень и включаете GitHub Pages в Settings → Pages, Source: branch = main, folder = /docs (или root).
- URL будет: https://YOUR_USERNAME.github.io/REPO_NAME/ (и если файл privacy_policy.md в корне, то https://YOUR_USERNAME.github.io/REPO_NAME/privacy_policy.html)
- Этот вариант удобен, если вы хотите хранить policy отдельно от "user page".

Шаги (Project Pages, web UI)
1. Создайте репозиторий, например CryptoPump-Policy (Public).
2. Добавьте папку docs и в ней файл privacy_policy.md (через Add file → Create new file).
3. Commit.
4. Перейдите в Settings → Pages (в левом меню).
5. В секции "Build and deployment" выберите "Deploy from a branch", укажите Branch: main and folder: /docs (или / (root) если кладёте index.md в корень).
6. Save, подождите пару минут.
7. URL будет указан на странице Settings → Pages, обычно https://YOUR_USERNAME.github.io/REPO_NAME/

Как выбрать — кратко
- Хочу простой URL (корень): создайте репозиторий username.github.io и положите index.md — тогда URL = https://username.github.io/
- Хочу держать policy рядом с проектом: используйте project pages, URL будет /REPO_NAME/

После публикации — включите HTTPS (обычно GitHub Pages автоматически включает HTTPS)
1. В Settings → Pages убедитесь, что опция "Enforce HTTPS" включена (Checkbox).
2. Откройте сайт по https:// — проверьте, что HTTPS работает.

Как подставить URL в приложение
- В MoreScreen.kt замените значение privacyPolicyUrl на финальный HTTPS URL, например:
  val privacyPolicyUrl = "https://umarrr9800.github.io/"  // если user page и index.md
  или
  val privacyPolicyUrl = "https://umarrr9800.github.io/cryptopump/privacy_policy.html" // project page variant

Проверьте в приложении:
1. Соберите и установите приложение (Run).
2. Откройте More → About → Privacy → Open website — убедитесь, что браузер открывает корректный URL.
3. Убедитесь, что ссылка доступна со смартфона (нет редиректов, TLS валиден).

Полезные заметки и отладка
- Если страница не появляется сразу — подождите 1–5 минут; иногда GitHub Pages деплой происходит с небольшой задержкой.
- Если видите 404: проверьте, что файл называется index.md (для root) или privacy_policy.md и деплой настроен на /docs если используете папку docs.
- Чтобы проверить статус Pages: Settings → Pages — там GitHub показывает build log и URL.
- Для публичной видимости используйте Public репозиторий — иначе Pages не будет работать для user pages.
- HTTPS: GitHub Pages автоматически предоставляет сертификат Let's Encrypt и включает HTTPS (можно включить Enforce HTTPS).

Дополнительно — автоматизация через GitHub (если потребуется)
- Вы можете использовать GitHub Actions для автоматического обновления страницы при пуше из другого репозитория (например из репозитория приложения), но это опция, не обязательная.

Безопасность/контент
- В тексте privacy policy укажите proxy URL и кратко опишите, что отправляется (у вас — только GET, заголовки и IP видны серверу).
- Проверьте лицензионные/правовые требования к использованию заголовков с investing.com (включите attribution: «Source: Investing.com»), если это требуется по условиям их сайта.

Если хотите — могу:
- 1) подготовить точные команды с вашим GitHub username и сгенерировать index.md с уже подставленным URL (вам останется только скопировать и выполнить команды), или
- 2) провести вас через web UI в реальном времени (пошагово), или
- 3) добавить в проект автоматическую проверку: если privacyPolicyUrl пуст, показывать встроенный текст; если задан — показывать кнопку «Open full Privacy Policy».

Скажите, какой вариант предпочитаете (A — user page username.github.io или B — project page), и если хотите — пришлю конкретную последовательность команд с вашим username подставленным.
