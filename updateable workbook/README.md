# Updateable Azure portal workbook

## Prerequisites
- [Excel on the web](https://www.office.com/launch/excel) (published to Onedrive for Business, SharePoint or Teams)
- [Microsoft 365 commercial or EDU plan that includes Office Scripts](https://docs.microsoft.com/en-us/microsoft-365/admin/manage/manage-office-scripts-settings)
- [Azure Logic App](https://docs.microsoft.com/en-us/azure/logic-apps/)
- [Azure Log Analytics Workspace](https://docs.microsoft.com/en-us/azure/azure-monitor/logs/log-analytics-workspace-overview)

## Instructions

- [Excel on the web](https://www.office.com/launch/excel) (published to Onedrive for Business, SharePoint or Teams) with an Office script to convert table data to json.
[![](https://github.com/Azure/cloud-rolesandops/blob/main/images/excelonweb.jpg)](https://github.com/Azure/cloud-rolesandops/blob/main/images/excelonweb.jpg))
- Office Script
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