<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Get Blogger Token</title>
</head>
<body>
  <h2>Getting Blogger Token...</h2>
  <script>
    const clientId = "974751408115-k66dfqlj9iopi1g6c11s9b1prlprn885.apps.googleusercontent.com";
    const redirectUri = window.location.origin + "/get-token.html";
    const scopes = [
      "https://www.googleapis.com/auth/blogger",
      "https://www.googleapis.com/auth/userinfo.email"
    ];

    function getAccessTokenFromUrl() {
      const hash = window.location.hash.substring(1);
      const params = new URLSearchParams(hash);
      return params.get("access_token");
    }

    const token = getAccessTokenFromUrl();

    if (token) {
      localStorage.setItem("blogger_token", token);
      // ប្រែទៅផ្ទាំង profile.html របស់បង (ប្តូរតាម URL របស់បង)
      window.location.href = "https://www.ponloe.org/p/profile.html";
    } else {
      const authUrl =
        "https://accounts.google.com/o/oauth2/v2/auth" +
        `?client_id=${clientId}` +
        `&redirect_uri=${encodeURIComponent(redirectUri)}` +
        "&response_type=token" +
        `&scope=${encodeURIComponent(scopes.join(" "))}` +
        "&include_granted_scopes=true";
      window.location.href = authUrl;
    }
  </script>
</body>
</html>
