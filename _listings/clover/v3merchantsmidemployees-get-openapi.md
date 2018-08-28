---
swagger: "2.0"
x-collection-name: Clover
x-complete: 0
info:
  title: Clover Get all employees
  version: 1.0.0
  description: Gives information for every employee associated to a merchant by default.
    Accepts optional filter and expand query parameters.
host: /merchants
basePath: https://api.clover.com
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /v3/merchants/{mId}/employees/{empId}/cash_events:
    get:
      summary: Get all cash events for an employee
      description: Retrieve cash events filtered by employee ID. Cash events can also
        be consumed by registering a Webhook callback. See https://docs.clover.com/build/webhooks/
      operationId: GetEmployeeCashEvents
      x-api-path-slug: v3merchantsmidemployeesempidcash-events-get
      parameters:
      - in: path
        name: empId
        description: Employee Id
      - in: query
        name: expand
        description: 'Expandable fields: [employee, device]'
      - in: query
        name: filter
        description: 'Filter fields: [employee'
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Employees
      - EmpId
      - Cash
      - Events
  /v3/merchants/{mId}/employees:
    get:
      summary: Get all employees
      description: Gives information for every employee associated to a merchant by
        default. Accepts optional filter and expand query parameters.
      operationId: GetEmployees
      x-api-path-slug: v3merchantsmidemployees-get
      parameters:
      - in: query
        name: expand
        description: 'Expandable fields: [roles, shifts]'
      - in: query
        name: filter
        description: 'Filter fields: [id, name, email, role, customId, role'
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
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