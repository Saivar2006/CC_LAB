# Ex.No: 04-GAE-Launcher

# Use GAE Launcher to Launch Web Applications

## AIM

To Use GAE launcher to launch the web applications.

## ALGORITHM

1. Create a new Cloud Console project or retrieve an existing project ID.
2. Go to the project page.
3. Install and initialize the Google Cloud SDK.
4. Download the SDK.
5. Create a website to host on Google App Engine.
6. Create the project structure with `app.yaml`, `www`, CSS, images and JavaScript directories/files as required.
7. Create the `app.yaml` configuration file.
8. Create `www/index.html`.
9. Configure `app.yaml` so the root URL serves `www/index.html` and other static files are served from `www`.
10. From the application root, run `gcloud app deploy`.
11. Use `gcloud app browse` to open the deployed application.
12. Verify that the web page is displayed.

## PROGRAM / CODE

```text
# app.yaml
runtime: python27
api_version: 1
threadsafe: true

handlers:
- url: /
  static_files: www/index.html
  upload: www/index.html
- url: /(.*)
  static_files: www/\1
  upload: www/(.*)

# www/index.html
<html>
<head>
<title>Hello, world!</title>
<link rel="stylesheet" type="text/css" href="/css/style.css">
</head>
<body>
<h1>Hello, world!</h1>
<p>This is a simple static HTML file that will be served from Google App Engine.</p>
</body>
</html>
```

## SAMPLE INPUT

```text
A Google Cloud project ID and a project directory containing app.yaml and www/index.html.
```

## SAMPLE OUTPUT

```text
The Hello World page is deployed successfully and can be opened at the App Engine application URL.
```

## RESULT

Thus a GAE launcher is used to launch the web applications and successfully executed.

---

### Files

- `README.md` – Complete experiment record
- `screenshots/` – Place your actual lab screenshots here

> **Note:** The content is organized from the supplied Cloud Computing Lab Manual. Where the manual gives a procedure rather than an algorithm or source program, that original procedure is preserved instead of inventing unrelated content.
