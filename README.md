## URL shortener using FAST API

### Endpoints

| Endpoint | HTTP Verb | Request body | Action |
| / | GET |  | Returns a static string output |
| /url | POST | Your URL target | Created url_key with additional info using secret key |
| /{url_key} | GET |  | Forwards to your target URL |
| /admin/{secret_key} | GET | Request body | Shows admin info about your shortened URL |
| /admin/{secret_key} | DELETE | Your secret key | Deletes your shortened URL |
