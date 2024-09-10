# PowerBI_Insights
Automatic insight generator from PowerBI web Reports and Dashboards
## Architecture
![Diagrama de arquitectura](https://github.com/jonruida/PowerBI_Insights/blob/main/assets/ARCH_INTERN.png)

## Data Extraction Approaches

### Native API Connectivity

#### Sources:
 -  [Github Available solutions for embedding Power BI content Repo](https://github.com/microsoft/PowerBI-Developer-Samples)
 -  Get Access Token Code, [Microfost Community Forum](https://community.fabric.microsoft.com/t5/Developer/REST-API-Get-Access-Token/m-p/1895937)

#### Option 1: [PowerShell Module `MicrosoftPowerBIMgmt`](https://github.com/jonruida/PowerBI_Insights/tree/main/Data_Extraction/Native_API_Con/Option_1) 
- **Sources**:
  - [Module doc](https://learn.microsoft.com/en-us/powershell/module/microsoftpowerbimgmt.reports/get-powerbireport?view=powerbi-ps)
- **Technologies/Strategies**:
  - Docker PowerShell container
  - Connect from container using PWSH native module
  - Get access token
  - **Status**: <span style="color:orange">PENDING</span>

- **Status**: 
  - <span style="color:red">Failed</span>

- **Report**:
  - Requires interaction with a browser, which is not convenient for use in an artifact. It would complicate things by needing Selenium or similar.
    ![Captura](https://github.com/jonruida/PowerBI_Insights/blob/main/assets/image.png)
  - Requires credentials, and it seems necessary to create an [Azure App](https://learn.microsoft.com/en-us/rest/api/power-bi/) for this. Gena is developed in Azure, nayways don't know if it's possible to use its credentials. 
- **Problem-Solving**:
  - (Add your solutions or alternatives here)

#### Option 2: REST API Connectivity

- **Technologies/Strategies**:
  - Authentication via OAuth2
  - Make HTTP requests from a Docker container
  - **Status**: <span style="color:orange">PENDING</span>

- **Status**: 
  - <span style="color:orange">In Progress</span>

- **Report**:
  - The REST API allows for more direct integration without the need for browser interaction.
  - Requires creating an application in  [Azure App](https://learn.microsoft.com/en-us/rest/api/power-bi/) to obtain access tokens.
  - The REST API documentation provides detailed examples of how to make the necessary requests.

- **Problem-Solving**:


#### Option 3: DirectQuery Connectivity

- **Technologies/Strategies**:
  - Configure DirectQuery to connect directly to data sources
  - Use Power BI Desktop to configure and publish reports
  - **Status**: <span style="color:orange">PENDING</span>

- **Status**: 
  - <span style="color:orange">In Progress</span>

- **Report**:
  - Requires configuration of data sources in PowerBI.

#### Option 4: Export Data
- **Sorces**:
  - [Forum](https://stackoverflow.com/questions/52079733/data-scraping-from-published-power-bi-visual)
- **Technologies/Strategies**:
  - Use the [Power BI Export Data feature](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-export-data)
  - Configure Power BI to allow data export
  - Make HTTP requests from a Docker container to export data
  - **Status**: <span style="color:orange">PENDING</span>

- **Status**: 
  - <span style="color:orange">In Progress</span>

- **Report**:
  - The Export Data feature allows you to export data from Power BI visualizations to Excel or CSV files.
  - Requires configuration of Power BI to grant export permissions.

- **Problem-Solving**:
- 
#### Option 5: [Power BI in Jupyter Notebooks](https://github.com/microsoft/powerbi-jupyter)
- **Sources**:
  - [Jupiter Notebook Github]
  - [PyPI](https://pypi.org/search/?q=Power+BI+report+demo.ipynb)

- **Technologies/Strategies**:
  - Use the [powerbiclient library](https://github.com/microsoft/powerbi-jupyter) to embed Power BI reports in Jupyter Notebooks
  - Authenticate using Azure AD or embed tokens
  - Export data from Power BI visuals directly within Jupyter Notebooks
  - **Status**: <span style="color:orange">PENDING</span>

- **Status**: 
  - <span style="color:orange">In Progress</span>

- **Report**:
  - Requires authentication via Azure AD or embed tokens to access Power BI reports.
  - The [documentation](https://github.com/microsoft/powerbi-jupyter/blob/main/DOCUMENTATION.md) provides detailed steps on how to install and use the library.

- **Problem-Solving**:


#### Option 6: Scanner API
- **Sources**:
  - Example (https://www.dataxbi.com/blog/2021/08/23/probando-scanner-api-power-bi/)
  - [Microsoft Doc](https://learn.microsoft.com/en-us/fabric/governance/metadata-scanning-overview)
- **Technologies/Strategies**:
  - Use the Power BI Scanner API to extract metadata from Power BI workspaces
  - Authenticate using Azure AD with service principal
  - Make HTTP requests from a Docker container to scan and retrieve metadata
  - **Status**: <span style="color:orange">PENDING</span>

- **Status**: 
  - <span style="color:orange">In Progress</span>

- **Report**:
  - The Scanner API allows you to extract detailed metadata from Power BI workspaces, including datasets, reports, dashboards, and more.
  - Requires proper configuration of Power BI and Azure AD to grant the necessary permissions for scanning.

## Additional Sections

### Feedback Section
- (Add a section for user feedback or issue reporting)

### Future Work
- (Outline any future plans or improvements)

### Contributors
- (List the contributors to the project)

### License
- (Specify the license under which the project is distributed)

!Diagrama de ejemplo

```mermaid
graph TD;
    A[Inicio] --> B[Proceso 1];
    A --> C[Proceso 2];
    B --> D[Fin];
    C --> D;
