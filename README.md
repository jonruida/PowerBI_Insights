# PowerBI_Insights
Automatic insight generator from PowerBI web Reports and Dashboards

## Approaches

### Native API Connectivity

#### Option 1: PowerShell Module `MicrosoftPowerBIMgmt`

- **Technologies/Strategies**:
  - Docker PowerShell container
  - Connect from container using PWSH native module
  - Get access token
  - **Status**: <span style="color:orange">PENDING</span>

- **Status**: 
  - <span style="color:red">Failed</span>

- **Report**:
  - Requires interaction with a browser, which is not convenient for use in an artifact. It would complicate things by needing Selenium or similar.
  - Requires credentials, and it seems necessary to create an Azure App for this.

- **Problem-Solving**:
  - (Add your solutions or alternatives here)

### Option 2: (Add your option title here)

- **Technologies/Strategies**:
  - (List the technologies and strategies here)
  - **Status**: <span style="color:orange">PENDING</span>

- **Status**: 
  - (Indicate the status here)

- **Report**:
  - (Describe the issues and findings here)

- **Problem-Solving**:
  - (Add your solutions or alternatives here)

### Option 3: (Add your option title here)

- **Technologies/Strategies**:
  - (List the technologies and strategies here)
  - **Status**: <span style="color:orange">PENDING</span>

- **Status**: 
  - (Indicate the status here)

- **Report**:
  - (Describe the issues and findings here)

- **Problem-Solving**:
  - (Add your solutions or alternatives here)

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
