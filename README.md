## URL shortener using FAST API

### Overview
Fast API implementation of a URL shortener,
Features 
1. Create a shortened URL
2. Forward to target URL using the shortened URL
3. Admin info - clicks on the shortened URL
4. Delete/ deactivate - Deactivate the shortened URL


### Getting started

1. Clone the project and change directory into the cloned folder
2. Create a virtual environment (venv) with python version above 3.6.5 
3. Activate the virtual environment and install the dependencies in the 
   requirements.txt
4. The sqlite database will be automatically created when the 
   application is started.
5. The sample of the environment variables file `.env.sample` is present 
   in the root directory, rename\copy this file to be `.env`
   The required env variables
   ```
   ENV_NAME="Replace with name of the environment eg: dev/local/prod"
   BASE_URL="Replace with the base URL eg: localhost:8000, domain_name"
   DB_URL="Replace with path to the db eg:sqlite:///./shortener.db"
   ```
6. Uvicorn is used as the application server, to start the application
   ```
   uvicorn shortener_app.main:app --reload
   ```
   
### Libraries used
- FastAPI
- SQLAlchemy
- uvicorn
- validators

### Endpoints

| Endpoint            | HTTP Verb | Request body    | Action                                                |
|---------------------|-----------|-----------------|-------------------------------------------------------|
| /                   | GET       |                 | Returns a static string output                        |
| /url                | POST      | Your URL target | Created url_key with additional info using secret key |
| /{url_key}          | GET       |                 | Forwards to your target URL                           |
| /admin/{secret_key} | GET       | Request body    | Shows admin info about your shortened URL             |
| /admin/{secret_key} | DELETE    | Your secret key | Deletes your shortened URL                            |


### License
Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0 Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

Copyright 2023 Nikhil Bhaskar