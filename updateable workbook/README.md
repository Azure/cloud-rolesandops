# Updateable Azure portal workbook

## Prerequisites
- [Excel on the web](https://www.office.com/launch/excel)
- [Microsoft 365 commercial or EDU plan that includes Office Scripts](https://docs.microsoft.com/en-us/microsoft-365/admin/manage/manage-office-scripts-settings)
- [Azure Logic App](https://docs.microsoft.com/en-us/azure/logic-apps/)
- [Azure Log Analytics Workspace](https://docs.microsoft.com/en-us/azure/azure-monitor/logs/log-analytics-workspace-overview)

## Instructions
- [Excel spreadsheet](https://github.com/Azure/cloud-rolesandops/releases/download/v0.91b/cromv09.xlsx) on the [web](https://www.office.com/launch/excel) (e.g., published to Onedrive for Business, SharePoint or Teams)
[![](/images/excelonweb.jpg)](/images/excelonweb.jpg)
- [Office script to convert table data to json](https://docs.microsoft.com/en-us/microsoft-365/admin/manage/manage-office-scripts-settings)
```typescript
function main(workbook: ExcelScript.Workbook): TableData[] {
  // Get the first table in the "mastertasklist" worksheet.
  // If you know the table name, use `workbook.getTable('TableName')` instead.
  // const table = workbook.getWorksheet('mastertasklist').getTables()[0];
  const table = workbook.getTable('TaskTable');

  // Get all the values from the table as text.
  const texts = table.getRange().getTexts();

  // Create an array of JSON objects that match the row structure.
  let returnObjects: TableData[] = [];
  if (table.getRowCount() > 0) {
    returnObjects = returnObjectFromValues(texts);
  }

  // Log the information and return it for a Power Automate flow.
  // console.log(JSON.stringify(returnObjects));
  return returnObjects
}

// This function converts a 2D array of values into a generic JSON object.
// In this case, we have defined the TableData object, but any similar interface would work.
function returnObjectFromValues(values: string[][]): TableData[] {
  let objectArray: TableData[] = [];
  let objectKeys: string[] = [];
  for (let i = 0; i < values.length; i++) {
    if (i === 0) {
      objectKeys = values[i]
      continue;
    }

    let object: { [key: string]: string } = {}
    for (let j = 0; j < values[i].length; j++) {
      object[objectKeys[j]] = values[i][j]
    }

    objectArray.push(object as unknown as TableData);
  }

  return objectArray;
}

interface TableData {
  systemAssignedId: string
  taskSet: string
  dateDefined: string
  dateCompleted: string
  systemAssignedDateNext: string
  systemAssignedStatus: string
  userAssignedStatus: string
  priority: string
  category: string
  technology: string
  tags: string
  task: string
  action: string
  accountable: string
  responsible: string
  consulted: string
  informed: string
  mode: string
  frequency: string
  systemAssignedFrequencyDays: string
  systemAssignedDaysSinceDateCompleted: string
  notes: string
  referenceUrl1: string
  referenceUrl2: string
}
```
- [Azure Logic App](https://docs.microsoft.com/en-us/azure/logic-apps/)

[<img src="/images/logicapp.jpg" width="750"/>](/images/logicapp.jpg)
- Updateable Azure portal workbook

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fcloud-rolesandops%2Fmain%2Fupdateable%2520workbook%2FPlanning%2520Guide%2520for%2520Cloud%2520Roles%2520and%2520Operations%2520Management%2520v0.92a.json)

(Workbook only - Excel and Logic App needs to be deployed separately)