## Running MCP Gateway without Docker MCP Toolkit


### Prerequisite

- Docker Desktop

### Clone the repo

```
git clone https://github.com/ajeetraina/demo-jira
cd demo-jira
```

## Add the right API Tokens

[Open this file](https://github.com/ajeetraina/demo-jira/blob/main/secrets/jira.env) and add the right API Token

```
atlassian.jira.api_token=XXX
atlassian.jira.personal_token=XX
atlassian.confluence.api_token=dummy
atlassian.confluence.personal_token=dummy
atlassian.jira.url=https://yourcompanyname.atlassian.net
atlassian.jira.username=your_username@companyname.com
```

The first two remains the same. Don't forget to change username and url.

## Bringing up MCP Gateway

```
docker compose up --build
```

You might see the result:

```
gateway-1  |   - Reading catalog from [https://desktop.docker.com/mcp/catalog/v2/catalog.yaml]
gateway-1  |   - Reading config from /config/config.yaml
gateway-1  | - Configuration read in 190.714417ms
gateway-1  | - Using images:
gateway-1  |   - mcp/atlassian@sha256:85b5a316edf04eeee782647ed50edb61a365a59ebe2c8f9c241834061a7d0ad6
gateway-1  | > Images pulled in 13.2895ms
gateway-1  | - Those servers are enabled: atlassian
gateway-1  | - Listing MCP tools...
gateway-1  |   - Running mcp/atlassian with [run --rm -i --init --security-opt no-new-privileges --cpus 1 --memory 2Gb --pull never -l docker-mcp=true -l docker-mcp-tool-type=mcp -l docker-mcp-name=atlassian -l docker-mcp-transport=stdio --network docker_default -e CONFLUENCE_API_TOKEN -e CONFLUENCE_PERSONAL_TOKEN -e JIRA_API_TOKEN -e JIRA_PERSONAL_TOKEN -e CONFLUENCE_URL -e CONFLUENCE_USERNAME -e JIRA_URL -e JIRA_USERNAME]
gateway-1  |   > atlassian: (37 tools)
gateway-1  | > 37 tools listed in 2.725245168s
gateway-1  | > Initialized in 2.93669371s
gateway-1  | > Start sse server on port 8811
```

