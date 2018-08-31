---
swagger: "2.0"
x-collection-name: Google Glass
x-complete: 0
info:
  title: Google Glass APIs Get Contact
  description: Gets a single contact by ID.
  contact:
    name: Google
    url: https://google.com
  version: v1
host: www.googleapis.com
basePath: /mirror/v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /accounts/{userToken}/{accountType}/{accountName}:
    post:
      summary: Insert Account
      description: Inserts a new account for a user
      operationId: mirror.accounts.insert
      x-api-path-slug: accountsusertokenaccounttypeaccountname-post
      parameters:
      - in: path
        name: accountName
        description: The name of the account to be passed to the Android Account Manager
      - in: path
        name: accountType
        description: Account type to be passed to Android Account Manager
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: userToken
        description: The ID for the user
      responses:
        200:
          description: OK
      tags:
      - Account
  /contacts:
    get:
      summary: Get Contacts
      description: Retrieves a list of contacts for the authenticated user.
      operationId: mirror.contacts.list
      x-api-path-slug: contacts-get
      responses:
        200:
          description: OK
      tags:
      - Contact
    post:
      summary: Insert Contact
      description: Inserts a new contact.
      operationId: mirror.contacts.insert
      x-api-path-slug: contacts-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Contact
  /contacts/{id}:
    delete:
      summary: Delete Contact
      description: Deletes a contact.
      operationId: mirror.contacts.delete
      x-api-path-slug: contactsid-delete
      parameters:
      - in: path
        name: id
        description: The ID of the contact
      responses:
        200:
          description: OK
      tags:
      - Contact
    get:
      summary: Get Contact
      description: Gets a single contact by ID.
      operationId: mirror.contacts.get
      x-api-path-slug: contactsid-get
      parameters:
      - in: path
        name: id
        description: The ID of the contact
      responses:
        200:
          description: OK
      tags:
      - Contact
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---