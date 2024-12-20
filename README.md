# TED SPARQL Editor[^1]

A web-based SPARQL query editor for exploring TED Open Data. This application allows users to write and execute SPARQL queries against the RDF database of the Publications Office (Cellar), view and download query results in multiple formats, and reuse queries in their applications via query URLs.

## Features

- Interactive SPARQL query editor
- Multiple result formats (JSON, HTML, XML, CSV, etc.)
- Direct downloads
- Reusable query URLs

## Live Version

Visit [TED SPARQL Editor](https://docs.ted.europa.eu/ted-sparql-editor) to use the live version of the application.

## Development Setup

### Prerequisites

- Node.js (v14 or higher)
- npm (v6 or higher)

### Installation & Running

1. Clone the repository:
    ```bash
    git clone https://github.com/OP-TED/ted-sparql-editor.git
    cd ted-sparql-editor
    ```

2. Install dependencies:
    ```bash
    npm install
    ```

3. Start the CORS proxy:
    ```bash
    npm start
    # or directly:
    node src/js/cors-proxy.js
    ```

4. Open the application:
    - Simply open the `index.html` file in your browser
    - The application will use the CORS proxy running on `http://localhost:8080` for all SPARQL queries

### Local Development Setup

The application consists of:
1. A static web interface (index.html and associated files)
2. A CORS proxy server for handling SPARQL queries

To run the application locally:
1. Start the CORS proxy using `npm start`
2. Open `index.html` in your web browser
3. That's it! No additional web server is needed

### Corporate Proxy Configuration

If you're behind a corporate proxy:

1. Set the proxy environment variables before starting the CORS proxy:
    ```bash
    # Windows
    set HTTP_PROXY=http://username:password@your.proxy.host:port
    set HTTPS_PROXY=http://username:password@your.proxy.host:port

    # Linux/Mac
    export HTTP_PROXY=http://username:password@your.proxy.host:port
    export HTTPS_PROXY=http://username:password@your.proxy.host:port
    ```

2. Or add them to your system environment variables permanently

### Environment Configuration

The application supports two environments:
- Production: Uses the live Cellar endpoint (production server)
- Test: Uses the Cellar endpoint dedicated for testing. 
  Caution: The test endpoint only contains sample data.

The endpoints are configured in `config.json`

## Third-Party Components

This project uses the following third-party components:

### Frontend Components
- **Bootstrap** (v5.3.0-alpha3)
  - Purpose: CSS framework for styling and components
  - License: MIT
  - Website: https://getbootstrap.com/

- **CodeMirror** (v5.65.2)
  - Purpose: Code editor with SPARQL syntax highlighting
  - License: MIT
  - Website: https://codemirror.net/

- **js-yaml** (v4.1.0)
  - Purpose: YAML parser and dumper
  - License: MIT
  - Website: https://github.com/nodeca/js-yaml

### Backend Components
- **Express** (v4.17.1)
  - Purpose: Web server framework
  - License: MIT
  - Website: https://expressjs.com/

- **cors** (v2.8.5)
  - Purpose: CORS middleware for Express
  - License: MIT
  - Website: https://github.com/expressjs/cors

- **node-fetch** (v2.6.1)
  - Purpose: Fetch API implementation for Node.js
  - License: MIT
  - Website: https://github.com/node-fetch/node-fetch

- **https-proxy-agent** (v7.0.5)
  - Purpose: HTTP(s) proxy agent for Node.js
  - License: MIT
  - Website: https://github.com/TooTallNate/node-https-proxy-agent

- **sparqljs** (v3.7.3)
  - Purpose: SPARQL query parser and generator
  - License: MIT
  - Website: https://github.com/RubenVerborgh/SPARQL.js

All third-party components are used under their respective licenses.

[^1]: _Copyright 2022 European Union_  
_Licensed under the EUPL, Version 1.2 or – as soon they will be approved by the European Commission – subsequent versions of the EUPL (the "Licence");_
_You may not use this work except in compliance with the Licence. You may obtain [a copy of the Licence here](LICENSE)._  
_Unless required by applicable law or agreed to in writing, software distributed under the Licence is distributed on an "AS IS" basis, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the Licence for the specific language governing permissions and limitations under the Licence._