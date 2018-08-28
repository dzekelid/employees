---
swagger: "2.0"
x-collection-name: Xero
x-complete: 0
info:
  title: Clarity Accounting X-related-model Employees
  description: X-related-model employees.
  contact:
    name: Xero Developer Team
    url: https://developer.xero.com
  version: "2.0"
host: api.xero.com
basePath: /api.xro/2.0
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /Employees:
    get:
      summary: Get Employees
      description: Get employees.
      operationId: getEmployees
      x-api-path-slug: employees-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Employees
    post:
      summary: Post Employees
      description: Post employees.
      operationId: postEmployees
      x-api-path-slug: employees-post
      parameters:
      - in: body
        name: Employees
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Employees
    put:
      summary: Put Employees
      description: Put employees.
      operationId: putEmployees
      x-api-path-slug: employees-put
      parameters:
      - in: body
        name: Employees
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Employees
    x-related-model:
      summary: X-related-model Employees
      description: X-related-model employees.
      operationId: x-related-modelEmployees
      x-api-path-slug: employees-xrelatedmodel
      responses:
        200:
          description: OK
      tags:
      - Employees
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