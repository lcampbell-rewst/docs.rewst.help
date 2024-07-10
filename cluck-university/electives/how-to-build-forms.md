# How to Build Forms

{% embed url="https://youtu.be/fgU7Cjz5JV4" %}

Forms are an important part of many automation workflows. They gather all the necessary information and ensure it's passed along to the right place. In Rewst, forms are not very different from other forms that you would use in real life.&#x20;

## Intro to Forms in Rewst

Building a form in Rewst is straightforward and can be efficiently done through the Automations section. This is where all of your existing forms will live. Here’s how to start:

1. **Navigate to Forms**:
   * Go to the dashboard.
   * Select `Automations` -> `Forms`. Here, you can view all existing forms.
2. **Create a New Form**:
   * Click the `+` button at the top right corner.
   * Enter a name for your form and click `Submit` to open the form editor.

### **Using the Form Editor**:

* **Drag and Drop**: Select different field types from the left panel and drag them to the right side to build your form.
* **Configure Fields**: Click on any field to modify names, add descriptions, set conditions, and more.
* **Preview and Save**: Use the preview option to check the form’s appearance and save your changes.

### **Field Configurations**

#### **General Settings**

* **Field Name**: Acts as a variable in your workflow, e.g., `ctx.hiring_manager` for capturing manager data.
* **Field Label**: The user-friendly name displayed on the form, such as `Hiring Manager`.

#### **Checkbox Options**

* **Required**: Ensures a field must be filled out to submit the form.
* **Hidden**: Keeps the field invisible unless a specific condition is met.
* **Auto Populate**: Automatically fills the field if there's only one option.
* **Allow Custom Input**: Allows users to enter a unique, one-time response.
* **Always Skip Cache**: Decides if fetching fresh data each time or using cached to speed up process.

## **Key Features of Forms in Rewst**

### **Field Conditions**

Field conditions enhance form functionality by enabling dynamic display or hiding of form fields based on user input or specific conditions.

**Example**: Show additional fields only if a user selects "Yes" to being the hiring manager. This ensures that irrelevant fields are not visible to users who do not meet certain criteria.

### **Dynamic Options**

Dynamic options automatically fetch data from integrations, thereby eliminating the need for manual data entry and keeping form options up-to-date with the latest data.

**Example**: If you are managing hiring information within your PSA (Professional Services Automation), dynamic options can automatically pull this data into the form, ensuring that users always have the most current information.

### **Embedding Forms**

Forms can be embedded within other web pages or platforms using an iframe. This allows for seamless integration of Rewst forms into your existing digital environment.

**To Embed a Form**: Go to the `View Usages` section next to the `Save` button in your form builder. Copy the dynamic form URL and use it to embed the form in an iframe.

## **Detailed Field Use Cases and Usage Examples**

Here's a breakdown of each field type, their purpose, and how they're referenced within form conditions via Jinja expressions.

### **Text/Markdown Field**

**Use Case**: Display static or dynamic text to the user.

```django
{{ CTX.<field_name>|d }}
```

### **Dropdown Field**

**Use Case**: Allows users to make a single selection from a list of predefined options.

```plaintext
{{ CTX.<field_name>.value|d }}
```

### **Multi-Select Field**

**Use Case**: Similar to a dropdown, but allows for multiple selections. Here are two examples, one for returning a specific item within the list, and one for checking if values are provided:

```django
{{ CTX.<field_name>[0].value|d }}
```

```django
{{ CTX.<field_name>|length > 0 }}
```

### **Checkbox Field**

**Use Case**: Used for capturing Boolean values (`True`/`False`).

```django
{{ CTX.<field_name>|d }}
```

### **Radio Buttons**

**Use Case**: Allows a single selection from multiple options.

```django
{{ CTX.<field_name>|d }}
```

### **Text Input**

**Use Case**: Captures single-line text input like names or identifiers.

```django
{{ CTX.<field_name>|d }}
```

### **Number Input**

**Use Case**: For inputting numerical values.

```django
{{ CTX.<field_name>|d }}
```

### **Multi-line Input**

**Use Case**: Allows for inputting text over multiple lines.

```django
{{ CTX.<field_name>|d }}
```

### **Date Input**

**Use Case**: For entering dates or times.

```django
{{ CTX.<field_name>|d }}
```
