---
swagger: "2.0"
x-collection-name: PayRun
x-complete: 0
info:
  title: Pay Run.IO Get employees from a pay schedule.
  description: Gets links to all employees included in the specified pay schedule.
  version: 17.18.6.206
host: api.test.payrun.io
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /Employer/{EmployerId}/Employees:
    get:
      summary: Get employees from employer.
      description: Get links to all employees for the specified employer.
      operationId: GetEmployeesFromEmployer
      x-api-path-slug: employeremployeridemployees-get
      parameters:
      - in: header
        name: Api-Version
        description: The version of the api to target
      - in: header
        name: Authorization
        description: The OAuth 1 authorization header
      - in: path
        name: EmployerId
        description: The employers unique identifier
      responses:
        200:
          description: OK
      tags:
      - Employees
      - From
      - Employer
  /Employer/{EmployerId}/Employees/Tag/{TagId}:
    get:
      summary: Get employees with tag
      description: Gets the employees with the tag
      operationId: GetEmployeesWithTag
      x-api-path-slug: employeremployeridemployeestagtagid-get
      parameters:
      - in: header
        name: Api-Version
        description: The version of the api to target
      - in: header
        name: Authorization
        description: The OAuth 1 authorization header
      - in: path
        name: EmployerId
        description: The employers unique identifier
      - in: path
        name: TagId
        description: The tag unique identifier
      responses:
        200:
          description: OK
      tags:
      - Employees
      - Tag
  /Employer/{EmployerId}/Employees/{EffectiveDate}:
    get:
      summary: Get employees from employer at a given effective date.
      description: Get links to all employees for the employer on specified effective
        date.
      operationId: GetEmployeesByEffectiveDate
      x-api-path-slug: employeremployeridemployeeseffectivedate-get
      parameters:
      - in: header
        name: Api-Version
        description: The version of the api to target
      - in: header
        name: Authorization
        description: The OAuth 1 authorization header
      - in: path
        name: EffectiveDate
        description: The effective date to be applied
      - in: path
        name: EmployerId
        description: The employers unique identifier
      responses:
        200:
          description: OK
      tags:
      - Employees
      - From
      - Employer
      - At
      - Given
      - Effective
      - Date
  /Employer/{EmployerId}/PaySchedule/{PayScheduleId}/Employees:
    get:
      summary: Get employees from a pay schedule.
      description: Gets links to all employees included in the specified pay schedule.
      operationId: GetEmployeesFromPaySchedule
      x-api-path-slug: employeremployeridpayschedulepayscheduleidemployees-get
      parameters:
      - in: header
        name: Api-Version
        description: The version of the api to target
      - in: header
        name: Authorization
        description: The OAuth 1 authorization header
      - in: path
        name: EmployerId
        description: The employers unique identifier
      - in: path
        name: PayScheduleId
        description: The pay schedules unique identifier
      responses:
        200:
          description: OK
      tags:
      - Employees
      - From
      - Pay
      - Schedule
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