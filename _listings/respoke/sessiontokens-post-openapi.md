---
swagger: "2.0"
x-collection-name: Respoke
x-complete: 0
info:
  title: Respoke Session Tokens
  description: An end-user client posts a tokenId from POST [base]/tokens to authenticate
    to an app as endpointId.
  termsOfService: https://www.respoke.io/files/respoke-tos-20141007.pdf
  version: v1
host: api.respoke.io
basePath: v1/
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  admin-sessions/:
    post:
      summary: Admin Sessions
      description: Log in with the account username and password. Get an Admin-Token.
      operationId: postAdminSessions
      x-api-path-slug: adminsessions-post
      parameters:
      - in: query
        name: password
        description: Your password
      - in: query
        name: username
        description: Your username
      responses:
        200:
          description: OK
      tags:
      - Admin
      - Sessions
  adminsessions/:
    post:
      summary: Permissions
      description: Full API permissions are obtained by POSTing your username and
        password to [base]/adminsessions.
      operationId: postAdminsessions
      x-api-path-slug: adminsessions-post
      parameters:
      - in: query
        name: password
        description: Your username
      - in: query
        name: username
        description: username
      responses:
        200:
          description: OK
      tags:
      - Adminsessions
  appauthsessions/:
    post:
      summary: App Auth Sessions
      description: Your users authenticate to Respoke using an App-Token obtained
        when they POST your tokenId to [base]/appauthsessions.
      operationId: postAppauthsessions
      x-api-path-slug: appauthsessions-post
      parameters:
      - in: query
        name: App-Token
        description: Your application token
      responses:
        200:
          description: OK
      tags:
      - Appauthsessions
  apps/:
    get:
      summary: Apps
      description: Create an app.
      operationId: getApps
      x-api-path-slug: apps-get
      parameters:
      - in: header
        name: Admin-Token
        description: Your admin token
      responses:
        200:
          description: OK
      tags:
      - Apps
  roles/:
    post:
      summary: Roles
      description: Create roleId and roleName for creating tokens.
      operationId: postRoles
      x-api-path-slug: roles-post
      parameters:
      - schema:
          $ref: '#/definitions/holder'
      - in: header
        name: App-Secret
        description: Your application secret
      responses:
        200:
          description: OK
      tags:
      - Roles
  session-tokens/:
    post:
      summary: Session Tokens
      description: An end-user client posts a tokenId from POST [base]/tokens to authenticate
        to an app as endpointId.
      operationId: postSessionTokens
      x-api-path-slug: sessiontokens-post
      parameters:
      - schema:
          $ref: '#/definitions/holder'
      - in: header
        name: App-Token
        description: Your application token
      responses:
        200:
          description: OK
      tags:
      - Session
      - Tokens
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