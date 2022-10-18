# Docker azure-agent
### :information_source: Information
Docker image for running a hosted agent.

### :books: Included
* `dotnet-sdk-3.1`
* `dotnet-sdk-6.0`


### :clipboard: Environment variables
| Name | Description |
| --- | --- |
| `AZP_URL` | The URL of the Azure DevOps or Azure DevOps Server instance. |
| `AZP_TOKEN` | Personal Access Token (PAT) with Agent Pools (read, manage) scope, created by a user who has permission to configure agents, at AZP_URL. |
| `AZP_AGENT_NAME` | Agent name (default value: the container hostname). |
| `AZP_POOL` | Agent pool name (default value: Default). |
| `AZP_WORK` | Work directory (default value: _work). |

### :computer: Example
Running the container installs the latest version of the agent, configures it, and runs the agent. It targets the Default pool of a specified Azure DevOps or Azure DevOps Server instance of your choice.

If you want a fresh agent container for every pipeline job, pass the --once flag to the run command.
```
docker run -e AZP_URL=<Azure DevOps instance> -e AZP_TOKEN=<PAT token> -e AZP_AGENT_NAME=mydockeragent dockeragent:latest
```

Optionally, you can control the pool and agent work directory by using additional environment variables.
```
docker run -e AZP_URL=<Azure DevOps instance> -e AZP_TOKEN=<PAT token> -e AZP_AGENT_NAME=mydockeragent dockeragent:latest --once
```

### :hearts: Acknowledgements
Taken from [Microsoft - Run a self-hosted agent in Docker](https://learn.microsoft.com/en-us/azure/devops/pipelines/agents/docker?view=azure-devops#linux) timestamp of `
06/03/2022`.
