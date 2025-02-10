API Test Cases

Endpoint: Update Pet /pet

Test Case 1: Successful update of pet's name

Description: Verify that updating the pet's name works correctly.

Preconditions:

A pet with id = 123, name = "Mur", status = "available" exists.

Steps:

Send a PUT request to /pet with body:

{ "id": 123, "name": "Updated Name", "status": "available" }

Verify response status code 200 OK.

Fetch the pet details and confirm that only the name field is updated.

Expected Result:

Status code 200 OK.

Name field updated to "Updated Name".

Other fields remain unchanged.

Test Case 2: Update pet with invalid ID

Description: Ensure that an invalid pet ID returns an error.

Steps:

Send a PUT request to /pet with an invalid id = -1.

Verify response status code 404 Not Found.

Check response message for a proper error description.

Expected Result:

Status code 404 Not Found.

Error message stating "Pet not found".

Test Case 3: Update pet with missing name field

Description: Ensure the request fails if the required name field is missing.

Steps:

Send a PUT request to /pet without the name field.

Verify response status code 400 Bad Request.

Check response body for validation error message.

Expected Result:

Status code 400 Bad Request.

Error message: "Name field is required".

Test Case 4: Unauthorized update attempt

Description: Ensure updating a pet requires authentication.

Steps:

Send a PUT request to /pet without authentication headers.

Verify response status code 401 Unauthorized.

Expected Result:

Status code 401 Unauthorized.

Error message indicating missing authentication.

Test Case 5: Verify status update functionality

Description: Ensure the pet's status is updated correctly.

Steps:

Update pet status from "available" to "sold".

Fetch the pet details.

Verify status field has changed.

Expected Result:

Status code 200 OK.

Status field updated to "sold".
