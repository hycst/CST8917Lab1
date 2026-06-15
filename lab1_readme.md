#### CST 8917 Lab1 Create and Deploy Azure Function

##### Course:** CST8917 – Serverless Applications

##### Student: Hesheng Yang


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
<img width="1731" height="950" alt="image" src="https://github.com/user-attachments/assets/c5f10c2f-fed1-4b40-b1cc-6cd48cbb3ede" />

##### Create Funcations app, and cogmos DB in Azure porta:

<img width="2991" height="1405" alt="image" src="https://github.com/user-attachments/assets/258819a8-1e02-48c7-badd-e90e675bdbe0" />


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

<img width="2994" height="1547" alt="image" src="https://github.com/user-attachments/assets/15b94ce1-ac6d-453f-b72a-26b08c76f20e" />




<img width="1746" height="852" alt="image" src="https://github.com/user-attachments/assets/3807ef43-de79-4603-a214-fb9c5fc40465" />



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


<img width="1728" height="1109" alt="image" src="https://github.com/user-attachments/assets/16ea8938-1538-40d6-8698-dcb3ea062dd9" />


##### Check Cosmos DB content:
<img width="2564" height="852" alt="image" src="https://github.com/user-attachments/assets/fca7ef4b-1832-4ba6-bd41-d901dd5d8cb0" />


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
