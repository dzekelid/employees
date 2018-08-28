swagger: "2.0"
x-collection-name: Xero
x-complete: 1
info:
  title: Xero oAuth 1a
  description: a-collection-to-authenticate-to-the-xero-api-using-oauth1-0a
  version: 1.0.0
host: api.xero.com
basePath: /
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
  /Employees/{EmployeeID}:
    get:
      summary: Get Employees Employee
      description: Get employees employee.
      operationId: getEmployeesEmployee
      x-api-path-slug: employeesemployeeid-get
      parameters:
      - in: path
        name: EmployeeID
      responses:
        200:
          description: OK
      tags:
      - Employees
      - EmployeeID
    post:
      summary: Post Employees Employee
      description: Post employees employee.
      operationId: postEmployeesEmployee
      x-api-path-slug: employeesemployeeid-post
      parameters:
      - in: path
        name: EmployeeID
      - in: body
        name: Employees
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Employees
      - EmployeeID
    x-related-model:
      summary: X-related-model Employees Employee
      description: X-related-model employees employee.
      operationId: x-related-modelEmployeesEmployee
      x-api-path-slug: employeesemployeeid-xrelatedmodel
      responses:
        200:
          description: OK
      tags:
      - Employees
      - EmployeeID