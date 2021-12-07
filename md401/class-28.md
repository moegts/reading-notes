# Django CRUD and Forms

## Working with forms

An HTML Form is a group of one or more fields/widgets on a web page, which can be used to collect information from users for submission to a server. Forms are a flexible mechanism for collecting user input because there are suitable widgets for entering many different types of data, including text boxes, checkboxes, radio buttons, date pickers and so on. Forms are also a relatively secure way of sharing data with the server, as they allow us to send data in POST requests with cross-site request forgery protection.

```html
### HTML Forms

> form action="/team_name_url/" method="post">

    <label for="team_name">Enter name: </label>
    <input id="team_name" type="text" name="name_field" value="Default name for team.">
    <input type="submit" value="OK">

/form>
```

## Main Things Django Does:-

- Display the default form the first time it is requested by the user.
- Receive data from a submit request and bind it to the form.
- Clean and validate the data.
- If any data is invalid, re-display the form, this time with any user populated values and error messages for the problem fields.
- If all data is valid, perform required actions (e.g. save the data, send an email, return the result of a search, upload a file, etc.)
- Once all actions are complete, redirect the user to another page.

The arguments that are common to most fields are listed below (these have sensible default values):

- **`required`**: If True, the field may not be left blank or given a None value. Fields are required by default, so you would set required=False to allow blank values in the form.

- **`label`**: The label to use when rendering the field in HTML. If a label is not specified, Django will create one from the field name by capitalizing the first letter and replacing underscores with spaces (e.g. Renewal date).

- **`label_suffix`**: By default, a colon is displayed after the label (e.g. Renewal date:). This argument allows you to specify a different suffix containing other character(s).

- **`initial`**: The initial value for the field when the form is displayed.

- **`widget`**: The display widget to use.

- **`help_text (as seen in the example above)`**: Additional text that can be displayed in forms to explain how to use the field.

- **`error_messages`**: A list of error messages for the field. You can override these with your own messages if needed.

- **`validators`**: A list of functions that will be called on the field when it is validated.

- **`localize`**: Enables the localization of form data input (see link for more information).

- **`disabled`**: The field is displayed but its value cannot be edited if this is True. The default is False.

It is also possible to have complete control over the rendering of each part of the form, by indexing its properties using dot notation. So, for example, we can access a number of separate items for our renewal_date field:

1- **{{ form.renewal_date }}**: The whole field.

2- **{{ form.renewal_date.errors }}**: The list of errors.

3- **{{ form.renewal_date.id_for_label }}**: The id of the label.

4- **{{ form.renewal_date.help_text }}**: The field help text.
