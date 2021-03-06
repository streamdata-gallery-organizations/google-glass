---
swagger: "2.0"
x-collection-name: Google Glass
x-complete: 0
info:
  title: Google Glass APIs Get Timelines
  description: Retrieves a list of timeline items for the authenticated user.
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
    patch:
      summary: Update Contact
      description: Updates a contact in place. This method supports patch semantics.
      operationId: mirror.contacts.patch
      x-api-path-slug: contactsid-patch
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: id
        description: The ID of the contact
      responses:
        200:
          description: OK
      tags:
      - Contact
    put:
      summary: Update Contact
      description: Updates a contact in place.
      operationId: mirror.contacts.update
      x-api-path-slug: contactsid-put
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: id
        description: The ID of the contact
      responses:
        200:
          description: OK
      tags:
      - Contact
  /locations:
    get:
      summary: Get Locations
      description: Retrieves a list of locations for the user.
      operationId: mirror.locations.list
      x-api-path-slug: locations-get
      responses:
        200:
          description: OK
      tags:
      - Location
  /locations/{id}:
    get:
      summary: Get Location
      description: Gets a single location by ID.
      operationId: mirror.locations.get
      x-api-path-slug: locationsid-get
      parameters:
      - in: path
        name: id
        description: The ID of the location or latest for the last known location
      responses:
        200:
          description: OK
      tags:
      - Location
  /settings/{id}:
    get:
      summary: Get Setting
      description: Gets a single setting by ID.
      operationId: mirror.settings.get
      x-api-path-slug: settingsid-get
      parameters:
      - in: path
        name: id
        description: The ID of the setting
      responses:
        200:
          description: OK
      tags:
      - Setting
  /subscriptions:
    get:
      summary: Get Subscriptions
      description: Retrieves a list of subscriptions for the authenticated user and
        service.
      operationId: mirror.subscriptions.list
      x-api-path-slug: subscriptions-get
      responses:
        200:
          description: OK
      tags:
      - Subscription
    post:
      summary: Create Subscription
      description: Creates a new subscription.
      operationId: mirror.subscriptions.insert
      x-api-path-slug: subscriptions-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Subscription
  /subscriptions/{id}:
    delete:
      summary: Delete Subscription
      description: Deletes a subscription.
      operationId: mirror.subscriptions.delete
      x-api-path-slug: subscriptionsid-delete
      parameters:
      - in: path
        name: id
        description: The ID of the subscription
      responses:
        200:
          description: OK
      tags:
      - Subscription
    put:
      summary: Update Subscription
      description: Updates an existing subscription in place.
      operationId: mirror.subscriptions.update
      x-api-path-slug: subscriptionsid-put
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: id
        description: The ID of the subscription
      responses:
        200:
          description: OK
      tags:
      - Subscription
  /timeline:
    get:
      summary: Get Timelines
      description: Retrieves a list of timeline items for the authenticated user.
      operationId: mirror.timeline.list
      x-api-path-slug: timeline-get
      parameters:
      - in: query
        name: bundleId
        description: If provided, only items with the given bundleId will be returned
      - in: query
        name: includeDeleted
        description: If true, tombstone records for deleted items will be returned
      - in: query
        name: maxResults
        description: The maximum number of items to include in the response, used
          for paging
      - in: query
        name: orderBy
        description: Controls the order in which timeline items are returned
      - in: query
        name: pageToken
        description: Token for the page of results to return
      - in: query
        name: pinnedOnly
        description: If true, only pinned items will be returned
      - in: query
        name: sourceItemId
        description: If provided, only items with the given sourceItemId will be returned
      responses:
        200:
          description: OK
      tags:
      - Timeline
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