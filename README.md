##Create a list in Sharepoint using HTTP.

#### Factors to consider

The original Power Automate uses The original template uses the SharePoint REST API and HTTP actions to create a list in SharePoint. It is a great example of how to use the SharePoint REST API. However, the template is limited in that it does not allow you to create a list with a custom content type. The template also does not allow you to specify the list template type. This sample addresses those limitations by using the SharePoint REST API and the Send an HTTP request to SharePoint action.

Template is here: https://flow.microsoft.com/en-us/galleries/public/templates/9c4c2b6d8a3a4e4ba5c8c3b4f4d2b1c2/create-a-list-in-sharepoint-using-http/

The original template uses the SharePoint REST API and HTTP actions to create a list in SharePoint. It is a great example of how to use the SharePoint REST API. However, the template is limited in that it does not allow you to create a list with a custom content type. The template also does not allow you to specify the list template type. This sample addresses those limitations by using the SharePoint REST API and the Send an HTTP request to SharePoint action.

#### Prerequisites

This sample requires the following:

* SharePoint Online or SharePoint Server 2013 or later.
* A SharePoint list to create.
* A SharePoint site with a document library to create a document library.
* A SharePoint content type to create a list with a custom content type.

#### Solution

action to create a list in Sharepoint is very powerful and easy to use. However, when you need to create a list in Sharepoint using HTTP, you can use this example. 

The example is based on the official documentation of Microsoft: [Create a list](https://docs.microsoft.com/en-us/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest#creating-a-list)

#### Code example

```javascript
{
  "method": "post",
  "headers": {
    "content-type": "application/json;odata=verbose",
    "accept": "application/json;odata=verbose",
    "X-RequestDigest": "@{body('Get_digest')?['d']?['__REQUESTDIGEST']}"
  },
  "body": {
    "__metadata": {
      "type": "SP.List"
    },
    "AllowContentTypes": true,
    "BaseTemplate": 100,
    "ContentTypesEnabled": true,
    "Description": "My list description",
    "Title": "My list title"
  },
  "uri": "@{concat(body('Get_site')?['d']?['Url'],'/_api/web/lists')"
}
```

#### Example of use

![Create a list in Sharepoint using HTTP](https://raw.githubusercontent.com/gsanchez-pl/PoSh/master/Sharepoint/Lists/Create%20a%20list%20in%20Sharepoint%20using%20HTTP/Sharepoint_Create_a_list_using_HTTP.png)

#### Tested on

- SharePoint Online
---

##Create a list in Sharepoint using HTTP with a custom template.

#### Factors to consider

The original Power Automate action to create a list in Sharepoint is very powerful and easy to use. However, when you need to create a list in Sharepoint using HTTP, you can use this example. 

The example is based on the official documentation of Microsoft: [Create a list](https://docs.microsoft.com/en-us/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest#creating-a-list)

#### Code example

```javascript
{
  "method": "post",
  "headers": {
    "content-type": "application/json;odata=verbose",
    "accept": "application/json;odata=verbose",
    "X-RequestDigest": "@{body('Get_digest')?['d']?['__REQUESTDIGEST']}"
  },
  "body]
[INFO] [streamChoices] [2023-11-07T10:17:08.304Z] solution 6 returned. finish reason: [length]
[INFO] [solutions] [2023-11-07T10:17:08.305Z] Open Copilot completion: [action **Create a list** is a premium action, so if you want to use it in your flow, you will need a premium license. The HTTP action is a standard action, so you can use it with any license.

#### How to use it

1. You need to know the URL of your Sharepoint site and the name of the list you want to create. For example, if your site is https://mycompany.sharepoint.com/sites/MySite and you want to create a list called MyList, you need to use the following URL: https://mycompany.sharepoint.com/sites/MySite/_api/web/lists

2. You need to know the body of the request. You can use the following body as a template:

```json
{
    "__metadata": {
        "type": "SP.List"
    },
    "AllowContentTypes": true,
    "BaseTemplate": 100,
    "ContentTypesEnabled": true,
    "Description": "My list description",
    "Title": "My list"
}
```

#### How to configure it

1. Add the HTTP action to your flow.

2. Configure the action as follows:

   - Method: POST
   - Uri: https://mycompany.sharepoint.com/sites/MySite/_api/web/lists
   - Headers:
     - Accept: application/json;odata=verbose
     - Content-Type: application/json;odata=verbose
     - X-RequestDigest: `Call the get digest action here`
   - Body: `Add the body here`

3. Add the **Get digest** action before the HTTP action and configure it as follows:

   - Site Address: https://mycompany.sharepoint.com/sites/MySite

4. Run the flow.

#### How to get the list id

1. Add the HTTP action to your flow.

2. Configure the action as follows:

   - Method: GET
   - Uri: https://mycompany.sharepoint.com/sites/MySite/_api/web/lists/getbytitle('MyList')
   - Headers:
     - Accept: application/json;odata=verbose
     - Content-Type: application/json;odata=verbose
     - X-RequestDigest: `Call the get digest action here`

3. Add the **Get digest** action before the HTTP action and configure it as follows:

   - Site Address: https://mycompany.sharepoint.com/sites/MySite

4. Run the flow.]
[INFO] [streamChoices] [2023-11-07T10:17:08.305Z] solution 5 returned. finish reason: [stop]
[INFO] [solutions] [2023-11-07T10:17:08.306Z] Open Copilot completion: [HTTP action that I used to create a list in Sharepoint was deprecated.  The new HTTP action is more complicated.  The new action requires an authentication token and a JSON payload.  The JSON payload is a list of fields and their data types.  The JSON payload is not intuitive and requires trial and error to get it right.  I have provided an example below that works for me.  I hope it helps you.

#### Example

```
{
    "content-type": "application/json",
    "odata-version": "4.0",
    "accept": "application/json;odata=nometadata",
    "IF-MATCH": "*",
    "X-HTTP-Method": "PUT"
}
```
```
{
    "Title": "Test List",
    "Description": "This is a test list.",
    "AllowContentTypes": true,
    "BaseTemplate": 100,
    "ContentTypesEnabled": true,
    "EnableAttachments": true,
    "EnableFolderCreation": true,
    "EnableMinorVersions": true,
    "EnableModeration": true,
    "EnableVersioning": true,
    "ForceCheckout": true,
    "Hidden": false,
    "NoCrawl": true,
    "OnQuickLaunch": true
}
```]
[INFO] [streamChoices] [2023-11-07T10:17:08.314Z] solution 4 returned. finish reason: [length]
[INFO] [solutions] [2023-11-07T10:17:08.315Z] Open Copilot completion: [action for creating a list in Sharepoint is limited to 256 columns. This is a problem when you have a list with more columns. This flow is a workaround for that limitation.

#### Prerequisites
- A Sharepoint site with the list you want to copy
- A Sharepoint site to copy the list to
- A Power Automate flow with the following actions:
  - HTTP
  - Parse JSON
  - Select
  - Create list item

#### Create a list in Sharepoint using HTTP

1. Create a new Power Automate flow
2. Add the HTTP action
3. Set the method to POST
4. Set the URI to the following: 
```
_api/web/lists
```
5. Set the Headers to the following: 
```
Content-Type: application/json;odata=verbose
```
6. Set the Body to the following:
```
{
  '__metadata': {
    'type': 'SP.List'
  },
  'AllowContentTypes': true,
  'BaseTemplate': 100,
  'ContentTypesEnabled': true,
  'Description': 'List created using HTTP',
  'Title': 'List created using HTTP'
}
```
7. Add the Parse JSON action
8. Set the Content to the Body of the HTTP action
9. Add the following schema to the schema editor:
```
{
    "type": "object",
    "properties": {
        "d": {
            "type": "object",
            "properties": {
                "__metadata": {
                    "type": "object",
                    "properties": {
                        "id": {
                            "type": "string"
                        },
                        "uri": {
                            "type": "string"
                        },
                        "etag": {
                            "type": "string"
                        },
                        "type": {
                            "type": "string"
                        }
                    },
                    "required": [
                        "id",
                        "uri",
                        "etag",
                        "type"
                    ]
                },
                "AllowContentTypes": {
                    "type": "boolean"
                },
                "BaseTemplate": {
                    "type": "integer"
                },
                "ContentTypesEnabled": {
                    "type": "boolean"
                },
                "Description": {
                    "type": "string"
                },
                "Title": {
                    "type": "string"
                }
            },
            "required": [
                "__metadata",
                "AllowContent]
[INFO] [streamChoices] [2023-11-07T10:17:08.316Z] solution 8 returned. finish reason: [length]
[INFO] [solutions] [2023-11-07T10:17:08.317Z] Open Copilot completion: [flow was created using the Sharepoint API, which is now deprecated. The current REST API is the recommended method. 

#### Steps

1. Create a Sharepoint list with the required columns. 
2. Create a Power Automate flow. 
3. Add a **HTTP** action. 
4. Set the **Method** to **POST**. 
5. Set the **URI** to: `https://<your-tenant>.sharepoint.com/sites/<your-site>/_api/web/lists/GetByTitle('<your-list-name>')/items` 
6. Set the **Headers** to: 
   * **Accept** : `application/json;odata=verbose` 
   * **Content-Type** : `application/json;odata=verbose` 
7. Set the **Body** to: 
   * **Title** : `Test` 
   * **Column1** : `Test1` 
   * **Column2** : `Test2` 
8. Save and run the flow. 
9. Check the Sharepoint list for the new item. 

#### References

* [Create a list item by using REST](https://docs.microsoft.com/en-us/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints#create-a-list-item-by-using-rest)
* [SharePoint REST API](https://docs.microsoft.com/en-us/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest)
* [Create a list item by using the SharePoint REST interface](https://docs.microsoft.com/en-us/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints#create-a-list-item-by-using-the-sharepoint-rest-interface)
* [Working with lists and list items with REST](https://docs.microsoft.com/en-us/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest)
* [Create SharePoint list items from an HTTP request](https://docs.microsoft.com/en-us/sharepoint/dev/business-apps/power-automate/guidance/create-sharepoint-list-items-from-an-http-request)
* [SharePoint REST API syntax for filtering list items](https://docs.microsoft.com/en-us/sharepoint/dev/general-development/sharepoint-rest-api-list-item-collection-v2#filtering)
* [SharePoint REST API syntax for selecting, filtering, sorting and paging](https://docs.microsoft.com/en-us/sharepoint/dev/general-development/sharepoint-rest-api-selecting-filtering-sorting-and-p]
[INFO] [streamChoices] [2023-11-07T10:17:08.318Z] solution 1 returned. finish reason: [length]
[INFO] [solutions] [2023-11-07T10:17:08.318Z] Open Copilot completion: [flow I made to create a list in Sharepoint using HTTP was to create a list with a single line of text. I am now trying to create a list with multiple columns. I am running into an issue where the list is created but the columns are not being added. I am using the same syntax as the single line of text flow but it is not working. I have tried many different ways to format the JSON but none of them have worked. I have also tried to create a list with multiple columns in the Sharepoint UI and then using the HTTP to get the JSON but it is not working either. I have attached my flow below. Any help would be greatly appreciated. Thanks in advance.

#### Flow

https://preview.redd.it/0x0qk7uq2kx61.png?width=1920&format=png&auto=webp&s=5a5e8f5f9a1f8d6e3e1d7d2a1c3d9f0a6c3a4f5d

#### JSON

    {
        "odata.metadata": "https://company.sharepoint.com/sites/SharepointSite/_api/$metadata#SP.List",
        "BaseTemplate": 100,
        "Title": "TestList",
        "Description": "TestList",
        "AllowContentTypes": true,
        "ContentTypesEnabled": true,
        "Hidden": false,
        "AllowDeletion": true,
        "EnableAttachments": true,
        "EnableFolderCreation": false,
        "EnableMinorVersions": true,
        "EnableModeration": false,
        "EnableVersioning": false,
        "NoCrawl": false,
        "ListExperienceOptions": 0,
        "MajorVersionLimit": 0,
        "MajorWithMinorVersionsLimit": 0,
        "DefaultContentApprovalWorkflowId": "00000000-0000-0000-0000-000000000000",
        "DraftVersionVisibility": 0,
        "ForceCheckout": false,
        "HasExternalDataSource": false,
        "HiddenList": false,
        "EnableAssignToEmail": false,
        "EnableFolderSync": false,
        "IsApplicationList": false,
        "IsCatalog": false,
        "IsPrivate": false,
        "MultipleDataList": false,
        "NoThrottleListOperations": false,
        "ServerTemplate]
[INFO] [streamChoices] [2023-11-07T10:17:08.319Z] solution 2 returned. finish reason: [DONE]
[INFO] [solutions] [2023-11-07T10:17:08.319Z] Open Copilot completion: [flow was created to take the data from the list and create a new list item in a different list. The list item that was created had a title and a body. The body contained the information from the original list. The body was a single line of text that was created using a combination of expressions. The expressions were used to create a JSON object that was converted to a string. The string was then passed into the body of the new list item. The JSON object was used to create a new list item in the new list.

#### How to use

The]
[INFO] [streamChoices] [2023-11-07T10:17:08.321Z] solution 9 returned. finish reason: [DONE]
[INFO] [solutions] [2023-11-07T10:17:08.321Z] Open Copilot completion: [flow was created to create a list in a SharePoint site. The flow was created using the SharePoint HTTP connector. The flow was tested using the HTTP connector and the SharePoint connector. 

The]
[INFO] [streamChoices] [2023-11-07T10:17:08.322Z] request done: headerRequestId: [f5b7249a-8af2-40d6-a62e-552d2a9cc03c] model deployment ID: [x10511ed45107]
