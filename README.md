# Create locally Linux VM to be used as self-hosted agent for AzureDevOps pipelines

1. Provision VM (here image: CentOS7)
2. Install initial packages (Java11 OpenJDK, Maven, GIT...)

## Configure agent and add token for AzureDevOps connection (one-time action)
1. Create directory for agent installation `mkdir myagent && cd myagent`
2. Download and extract installation files<br>
`wget https://vstsagentpackage.azureedge.net/agent/2.211.1/vsts-agent-linux-x64-2.211.1.tar.gz`<br>
`tar zxvf vsts-agent-linux-x64-2.211.1.tar.gz`
3. Run `config.sh` to install and configure agent. You need to have agent pool already created in AzureDevOps. On this step you add Azure DevOps token.
4. `sudo ./svc.sh install vagrant` (by each next VM start agent is started and connected to AzureDevOps automatically).
5. `sudo ./svc.sh start` and check if running `sudo ./svc.sh status`.
6. Check Azure DevOps portal if your agent is available and run sample pipeline defining usage of this agent.

<footer>  </footer>
