# Data Table

## Introduction

Welcome to the Data Table component documentation! As part of the page builder in App Platform, the Data Table component allows you to display and manage rows of data in a structured, tabular format. This component is essential for MSPs to handle large datasets efficiently, such as client information, service logs, or performance metrics, providing a clear and interactive view of data.

## Why we developed it

The Data Table component facilitates the organization, interaction, and analysis of complex data within web applications. It provides tools for sorting, filtering, and paging through data, which helps users manage large amounts of information without losing track of their data's context or structure. This is particularly useful in environments where quick data retrieval and clear data presentation are crucial for decision-making and operational efficiency.

## What it could be used for

* Displaying detailed lists of customer tickets and their statuses.
* Managing inventory levels across multiple client sites.
* Showcasing performance reports with sortable metrics.
* Organizing billing and transaction records for easy access and analysis.

## **Example \ Use Case**

Consider a scenario where an MSP needs to monitor and manage network equipment across various client sites. The Data Table component can be used to list all equipment, displaying columns for device type, status, last service date, and location. Technicians can quickly sort by any column to prioritize devices that require immediate attention or filter to view only certain types of equipment. This use of the Data Table simplifies the management of numerous devices, ensuring that maintenance is timely and no critical issues are overlooked.

## Adding a Data Table to your page

1. **Access the Canvas**: Open the page you're working on in edit mode, in App Platform.
2. **Drag-and-Drop**: Locate the 'Data Table' component in the component library, then drag and drop it onto the canvas.

## Configuring the Data Table component

1. **Select the component**: Click on the added 'Data Table' component to select it.
2. **Properties Panel**: On the properties panel, you'll find various configurable options:
   * **Data Source**
     * **Add\Edit Data Source**
       * **Data Load Method**: Specify when the chosen workflow will execute; Use Latest Workflow' or 'Run workflow on load'.
       * **Workflow**: Specify the workflow to load.
       * **Open in new tab**: Open the specified workflow in a new tab.
       * **Workflow Output**: Specify the output of the workflow to populate the data table.
   * **Table Configuration**
     * **Add a column**
       * **Accessor**: Specify the accessor (key) to access the data for the column.
       * **Type**: Set the data type; 'none', 'string', 'number', 'boolean', 'object', 'array' or 'action'.
       * **Header**: Specify the Header for the column.
       * **Button**: Select the desired icon for the button.
       * **Button Function**: Set the behavior of the button when clicked; 'Run a Workflow', 'Open a link' or 'Run Typescript'.
         * **Workflow**: Select the workflow to run
         * **Link**: Specify the URL to redirect to.
       * **Run Function on edit**: Toggle to run the button function when the component is edited.
       * **Reload Table after function**: Toggle to allow a refresh of the data table content once the function has completed.
     * **Edit Column**
       * **Accessor**: Specify the accessor (key) to access the data for the column.
       * **Type**: Set the data type; 'none', 'string', 'number', 'boolean', 'object', 'array' or 'action'.
       * **Header**: Specify the Header for the column.
       * **Add a condition**: Set rules to dynamically alter the styling of the cell data.
       * **Column Specific Configuration**
         * **Enable Editing** - Toggle to enable\disable editing of data in the column.
         * **Enable Click To Copy** - Toggle to enable\disable copying of data in the column.
         * **Enable Column Dragging** - Toggle to enable\disable column resizing.
         * **Enable Column Ordering** - Toggle to enable\disable column ordering.
         * **Enable Column Sorting** - Toggle to enable\disable column sorting.
         * **Enable Column Actions** - Toggle to enable\disable column actions.
       * **Column Aggregation Settings**
         * **Aggregate Group Function** - Specify a method to group similar values.
         * **Aggregate Footer Function** - Specify a method to count\visualize values.
       * **Edit Table Configuration**: An array of component specific toggle's to modify the overall look and feel of the data table component.
3. **Live Preview**: The canvas provides a live preview of your configured component(s) once you've made changes.



If you have any questions or need assistance, feel free to reach out to our support team.\
&#x20;\- Happy designing! 🎨🚀
