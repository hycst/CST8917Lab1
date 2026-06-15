#### CST 8917 Lab1 Create and Deploy Azure Function

**Course:** CST8917 – Serverless Applications
**Student: Hesheng Yang


##### Prerequisites

Install the following software before running the project:

- Python 3.12
- Visual Studio Code
- Azure Functions Core Tools v4
- Azure Functions Extension for VS Code
- Azurite Storage Emulator
- Azure CLI (optional)
- Azure Cosmos DB account

#####  Install Dependencies
pip install -r requirements.txt



##### Required Environment Variables

Create a file named **local.settings.json** in the project root.

Format:

```json
{
  "IsEncrypted": false,
  "Values": {
    "FUNCTIONS_WORKER_RUNTIME": "python",
    "AzureWebJobsStorage": "UseDevelopmentStorage=true",

    "COSMOS_ENDPOINT": "<the cosmos-endpoint, which can find from Azure Portal>",
    "COSMOS_KEY": "<the cosmos Primay key, which can find from Azure Portal>",
    "COSMOS_DATABASE_NAME": "TextAnalyzerDB",
    "COSMOS_CONTAINER_NAME": "AnalysisHistory"
  }
}

```


##### Start Azurite

From VS Code:

- Run **Azurite: Start**

Watch the output:
```
Functions:

TextAnalyzer:
http://localhost:7071/api/TextAnalyzer

GetAnalysisHistory:
http://localhost:7071/api/GetAnalysisHistory
```


###### Test the APIs: Analyze Text

GET request

```
http://localhost:7071/api/TextAnalyzer?text=Serverless%20computing%20is%20amazing.
```

##### Retrieve History

```
http://localhost:7071/api/GetAnalysisHistory
```

Limit the number of records:

```
http://localhost:7071/api/GetAnalysisHistory?limit=5
```

---

#### Function Code:
https://github.com/hycst/CST8917Lab1/blob/main/function_app.py

#### Requirements:
[azure-functions
azure-cosmos](https://github.com/hycst/CST8917Lab1/blob/main/requirements.txt)

https://github.com/hycst/CST8917Lab1/blob/main/requirements.txt

#### Database Documentation:
https://github.com/hycst/CST8917Lab1/blob/main/database_choice.md

#### Demo Video Link:
https://youtu.be/vKO75aeR6ks
