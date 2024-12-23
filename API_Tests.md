1. Create Contact (403 Test)
Description: Attempt to create a contact when the token does not have access to a location.
Expected Result: 403 Forbidden

Method: POST
URL: https://services.leadconnectorhq.com/contacts
Headers:
Header	Required	Description	Example
Authorization	Yes	Bearer token for auth.	Bearer pit-84ec65c2-b205-4967-8371-0ff3dbe3ae47
Content-Type	Yes	Request payload format.	application/json
Accept	Yes	Expected response format.	application/json
Version	Yes	API version.	2021-07-28
Body:
json
Copy code
{
    "firstName": "John",
    "lastName": "Doe",
    "email": "john.doe@example.com"
}




2. Create Contact (400 Test)
Description: Send malformed JSON.
Expected Result: 400 Bad Request

Method: POST
URL: https://services.leadconnectorhq.com/contacts
Headers:
Header	Required	Description	Example
Authorization	Yes	Bearer token for auth.	Bearer pit-84ec65c2-b205-4967-8371-0ff3dbe3ae47
Content-Type	Yes	Request payload format.	application/json
Accept	Yes	Expected response format.	application/json
Version	Yes	API version.	2021-07-28
Body (Malformed JSON):
json
Copy code
{
    "firstName": "John",
    "lastName": "Doe"
    "email": "john.doe@example.com"
}





3. Create Contact (201 Test)
Description: Provide valid data and correct access.
Expected Result: 201 Created

Method: POST
URL: https://services.leadconnectorhq.com/contacts
Headers:
Header	Required	Description	Example
Authorization	Yes	Bearer token for auth.	Bearer pit-84ec65c2-b205-4967-8371-0ff3dbe3ae47
Content-Type	Yes	Request payload format.	application/json
Accept	Yes	Expected response format.	application/json
Version	Yes	API version.	2021-07-28
Body:
json
Copy code
{
    "firstName": "Jane",
    "lastName": "Smith",
    "email": "jane.smith@example.com",
    "phone": "+123456789"
}





4. Get Contact (200 Test)
Description: Retrieve a previously created contact.
Expected Result: 200 OK

Method: GET
URL: https://services.leadconnectorhq.com/contacts/{contactId}
Headers:
Header	Required	Description	Example
Authorization	Yes	Bearer token for auth.	Bearer pit-84ec65c2-b205-4967-8371-0ff3dbe3ae47
Accept	Yes	Expected response format.	application/json
Body:
No body is required.




5. Get Contact (400 Test)
Description: Attempt to retrieve a non-existent contact.
Expected Result: 400 Not Found

Method: GET
URL: https://services.leadconnectorhq.com/contacts/{invalidContactId}
Headers:
Header	Required	Description	Example
Authorization	Yes	Bearer token for auth.	Bearer pit-84ec65c2-b205-4967-8371-0ff3dbe3ae47
Accept	Yes	Expected response format.	application/json
Body:
No body is required.





6. Update Contact (200 Test)
Description: Successfully update an existing contact.
Expected Result: 200 OK

Method: PUT
URL: https://services.leadconnectorhq.com/contacts/{contactId}
Headers:
Header	Required	Description	Example
Authorization	Yes	Bearer token for auth.	Bearer pit-84ec65c2-b205-4967-8371-0ff3dbe3ae47
Content-Type	Yes	Request payload format.	application/json
Body:
json
Copy code
{
    "firstName": "UpdatedName",
    "lastName": "UpdatedLastName",
    "phone": "+987654321"
}





7. Update Contact (422 Test)
Description: Submit unprocessable data.
Expected Result: 422 Unprocessable Entity

Method: PUT
URL: https://services.leadconnectorhq.com/contacts/{contactId}
Headers:
Header	Required	Description	Example
Authorization	Yes	Bearer token for auth.	Bearer pit-84ec65c2-b205-4967-8371-0ff3dbe3ae47
Content-Type	Yes	Request payload format.	application/json
Body:
json
Copy code
{
    "phone": "invalidPhoneFormat"
}




8. Delete Contact (200 Test)
Description: Remove a contact.
Expected Result: 200 OK

Method: DELETE
URL: https://services.leadconnectorhq.com/contacts/{contactId}
Headers:
Header	Required	Description	Example
Authorization	Yes	Bearer token for auth.	Bearer pit-84ec65c2-b205-4967-8371-0ff3dbe3ae47
Body:
No body is required.
