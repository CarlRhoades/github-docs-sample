# Private repositories

A public repository is read in the browser from `raw.githubusercontent.com`. Nothing in the web part holds a credential.

A private repository is different. The browser calls an HTTPS function that you host. The function holds the GitHub credential and returns the file. The web part never sees the token.

Set the web part like this:

1. **Source:** Private repository through a proxy.
2. **Proxy URL:** `https://<your-function>.azurewebsites.net/api/content`.
3. **Entra application ID URI:** `api://<application-id>`.

The function allows one owner and one or more repositories. A call for any other repository is rejected. Turn on Entra authentication on the function before you store a token in it. An anonymous function will serve the allow-listed repository to anyone who can reach the URL.

The setup steps are in the project README.
