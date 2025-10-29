# orm-mcp-launcher


[![Install O’Reilly MCP](https://img.shields.io/badge/VS_Code-Install_O%E2%80%99Reilly_MCP-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://vscode.dev/redirect/mcp/install?name=oreilly.content-discovery-dev&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.oreilly.review%2Fapi%2Fcontent-discovery%2Fv1%2Fmcp%2F%22%2C%22headers%22%3A%7B%22Authorization%22%3A%22Token%20%24%7BOREILLY_API_KEY%7D%22%7D%7D)


# Cursor

Perfect — here’s a **drop-in “Click to Launch” badge + fallback section** for your README that works whether or not Cursor supports `cursor://` links.

It provides a nice badge for users who have the protocol handler, and clear manual steps for everyone else.

---

### 🟠 Complete README Snippet

You can quickly add the O’Reilly Content-Discovery MCP to **Cursor** using the badge below.  
This lets Cursor query the O’Reilly API securely using your local API key.

[![Click to Launch in Cursor](https://img.shields.io/badge/Launch_in_Cursor-O%E2%80%99Reilly_MCP-FF9900?style=flat-square&logo=cursor&logoColor=white)](cursor://mcp/install?config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.oreilly.review%2Fapi%2Fcontent-discovery%2Fv1%2Fmcp%2F%22%2C%22headers%22%3A%7B%22Authorization%22%3A%22Token%20%24%7BOREILLY_API_KEY%7D%22%7D%7D)

> ⚠️ **Note:**  
> The above button will only work if Cursor has registered the `cursor://` protocol on your system (this may vary by OS or version).

---

### 🧩 Manual Setup (Fallback)

If clicking the badge doesn’t launch Cursor automatically, you can configure it manually:

1. Open **Cursor → Settings → MCP Servers → Add New Server**
2. Paste the following JSON config:

```json
   {
     "mcpServers": {
       "oreilly.content-discovery-dev": {
         "type": "http",
         "url": "https://api.oreilly.review/api/content-discovery/v1/mcp/",
         "headers": {
           "Authorization": "Token ${OREILLY_API_KEY}"
         }
       }
     }
   }
```

3. Set your API key as an environment variable before launching Cursor:

   **macOS / Linux**

   ```bash
   export OREILLY_API_KEY="your-real-token"
   ```

   **Windows (PowerShell)**

   ```powershell
   $Env:OREILLY_API_KEY="your-real-token"
   ```

4. Restart Cursor, and it will automatically substitute the value of
   `${OREILLY_API_KEY}` into the authorization header when connecting.

---

### ✅ Verify it works

Open Cursor’s Developer Tools (⇧⌘I or Ctrl+Shift+I) → **Network tab** → check that requests to
`https://api.oreilly.review/api/content-discovery/v1/mcp/` include the header:

```
Authorization: Token <your-token-here>
```

If you see that header, your MCP connection is correctly configured. 🎉

