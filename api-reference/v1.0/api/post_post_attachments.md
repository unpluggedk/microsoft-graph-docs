# Create Attachment

Use this API to add an [attachment](../resources/attachment.md) to a post. Since there
is currently a limit of 4MB on the total size of each REST request, this limits the size of the attachment
you can add to under 4MB.
### Prerequisites
One of the following **scopes** is required to execute this API: 

* Group.ReadWrite.All
 
### HTTP request
<!-- { "blockType": "ignored" } -->
Attachments for a [post](../resources/post.md) in a [thread](../resources/thread.md) belonging to a [conversation](../resources/conversation.md) of a group.
```http
POST /groups/<id>/threads/<id>/posts/<id>/attachments
POST /groups/<id>/conversations/<id>/threads/<id>/posts/<id>/attachments
```
### Request headers
| Header       | Value |
|:---------------|:--------|
| Authorization  | Bearer <token>. Required.  |

### Request body
In the request body, supply a JSON representation of [Attachment](../resources/attachment.md) object.


### Response
If successful, this method returns `201, Created` response code and [Attachment](../resources/attachment.md) object in the response body.

### Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "create_attachment_from_post"
}-->
```http
Creating file attachment 
POST https://graph.microsoft.com/v1.0/groups/<id>/threads/<id>/posts/<id>/attachments
Content-type: application/json
Content-length: 142

{
  "@odata.type": "#Microsoft.OutlookServices.FileAttachment",
  "name": "name-value",
  "contentType": "contentType-value",
  "isInline": false,
  "contentLocation": "contentLocation-value",
  "contentBytes": "contentBytes-value"
}

Creating item attachment
POST https://graph.microsoft.com/v1.0/groups/<id>/threads/<id>/posts/<id>/attachments
Content-type: application/json
Content-length: 100

{
  "@odata.type": "#Microsoft.OutlookServices.ItemAttachment",
  "name": "name-value",
  "item": "message or event entity"
}
```
In the request body, supply a JSON representation of [attachment](../resources/attachment.md) object.
##### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.attachment"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 162

{
  "lastModifiedDateTime": "datetime-value",
  "name": "name-value",
  "contentType": "contentType-value",
  "size": 99,
  "isInline": true,
  "id": "id-value"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Create Attachment",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->