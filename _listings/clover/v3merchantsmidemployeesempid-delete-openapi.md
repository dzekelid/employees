---
swagger: "2.0"
x-collection-name: Clover
x-complete: 0
info:
  title: Clover Delete an employee
  version: 1.0.0
  description: Deletes a single employee from a merchant. Third party developers cannot
    delete the 'owner' employee.
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
    post:
      summary: Create an employee
      description: Creates an employee for a merchant. Accepts optional expand parameters.
      operationId: CreateEmployee
      x-api-path-slug: v3merchantsmidemployees-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: expand
        description: 'Expandable fields: [shifts, payments, orders, roles]'
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Employees
  /v3/merchants/{mId}/employees/{empId}:
    get:
      summary: Get a single employee
      description: Returns information for a single employee.  Accepts optional expand
        query parameters
      operationId: GetEmployee
      x-api-path-slug: v3merchantsmidemployeesempid-get
      parameters:
      - in: path
        name: empId
        description: Employee Id
      - in: query
        name: expand
        description: 'Expandable fields: [roles, shifts]'
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
    post:
      summary: Update an employee
      description: Updates information for a single employee. Accepts optional expand
        query params.
      operationId: UpdateEmployee
      x-api-path-slug: v3merchantsmidemployeesempid-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: empId
        description: Employee Id
      - in: query
        name: expand
        description: 'Expandable fields: [shifts, payments, orders, roles]'
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
    delete:
      summary: Delete an employee
      description: Deletes a single employee from a merchant. Third party developers
        cannot delete the 'owner' employee.
      operationId: DeleteEmployee
      x-api-path-slug: v3merchantsmidemployeesempid-delete
      parameters:
      - in: path
        name: empId
        description: Employee Id
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
  /v3/merchants/{mId}/employees/{empId}/shifts:
    get:
      summary: Get all shifts for an employee
      description: Get all shifts for an employee.
      operationId: GetEmployeeShifts
      x-api-path-slug: v3merchantsmidemployeesempidshifts-get
      parameters:
      - in: path
        name: empId
        description: Employee Id
      - in: query
        name: expand
        description: 'Expandable fields: [employee, overrideInEmployee, overrideOutEmployee]'
      - in: query
        name: filter
        description: 'Filter fields: [id, employee'
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
      - Shifts
    post:
      summary: Create shift for an employee
      description: Create shift for an employee.
      operationId: CreateShift
      x-api-path-slug: v3merchantsmidemployeesempidshifts-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: empId
        description: Employee Id
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
      - Shifts
  /v3/merchants/{mId}/employees/{empId}/shifts/{shiftId}:
    get:
      summary: Get a single shift
      description: Get a single shift.
      operationId: GetEmployeeShift
      x-api-path-slug: v3merchantsmidemployeesempidshiftsshiftid-get
      parameters:
      - in: path
        name: empId
        description: Employee Id
      - in: query
        name: expand
        description: 'Expandable fields: [employee, overrideInEmployee, overrideOutEmployee]'
      - in: path
        name: mId
        description: Merchant Id
      - in: path
        name: shiftId
        description: Employee Shift Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Employees
      - EmpId
      - Shifts
      - ShiftId
    post:
      summary: Update a single shift
      description: Update a single shift.
      operationId: UpdateShift
      x-api-path-slug: v3merchantsmidemployeesempidshiftsshiftid-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: empId
        description: Employee Id
      - in: query
        name: expand
        description: 'Expandable fields: [employee, overrideInEmployee, overrideOutEmployee]'
      - in: path
        name: mId
        description: Merchant Id
      - in: path
        name: shiftId
        description: Employee Shift Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Employees
      - EmpId
      - Shifts
      - ShiftId
    delete:
      summary: Delete a single shift
      description: Delete a single shift.
      operationId: DeleteShift
      x-api-path-slug: v3merchantsmidemployeesempidshiftsshiftid-delete
      parameters:
      - in: path
        name: empId
        description: Employee Id
      - in: path
        name: mId
        description: Merchant Id
      - in: path
        name: shiftId
        description: Employee Shift Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Employees
      - EmpId
      - Shifts
      - ShiftId
  /v3/merchants/{mId}/employees/{empId}/orders:
    get:
      summary: Get all orders for an employee
      description: Get all orders for an employee.
      operationId: GetEmployeeOrders
      x-api-path-slug: v3merchantsmidemployeesempidorders-get
      parameters:
      - in: path
        name: empId
        description: Employee Id
      - in: query
        name: expand
        description: 'Expandable fields: [lineItems, customers, payments, credits,
          refunds, serviceCharge, discounts]'
      - in: query
        name: filter
        description: 'Filter fields: [lineItems, customers, payments, credits, refunds,
          serviceCharge, discounts]'
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
      - Orders
  /v3/merchants/{mId}/employees/{empId}/payments:
    get:
      summary: Get all payments under an employee
      description: Get all payments under an employee.
      operationId: GetEmployeePayments
      x-api-path-slug: v3merchantsmidemployeesempidpayments-get
      parameters:
      - in: path
        name: empId
        description: Employee Id
      - in: query
        name: expand
        description: 'Expandable fields: [cardTransaction, dccInfo, germanInfo, appTracking,
          taxRates, lineItemPayments, refunds, order, tender, employee, transactionInfo]'
      - in: query
        name: filter
        description: 'Filter fields: [modifiedTime, voidReason, cardTransaction'
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
      - Payments
  /v3/merchants/{mId}/employee_cards:
    post:
      summary: Add employee cards
      description: .Add employee cards
      operationId: CreateOrUpdateEmployeeCard
      x-api-path-slug: v3merchantsmidemployee-cards-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Employee
      - Cards
    get:
      summary: Get employee cards
      description: .Get employee cards
      operationId: GetEmployeeCards
      x-api-path-slug: v3merchantsmidemployee-cards-get
      parameters:
      - in: query
        name: filter
        description: 'Filter fields: [id, employee'
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Employee
      - Cards
  /v3/merchants/{mId}/employee_cards/{employeeCardId}:
    get:
      summary: Get employee card
      description: .Get employee card
      operationId: GetEmployeeCard
      x-api-path-slug: v3merchantsmidemployee-cardsemployeecardid-get
      parameters:
      - in: path
        name: employeeCardId
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Employee
      - Cards
      - EmployeeCardId
    delete:
      summary: Delete employee cards
      description: .Delete employee cards
      operationId: DeleteEmployeeCard
      x-api-path-slug: v3merchantsmidemployee-cardsemployeecardid-delete
      parameters:
      - in: path
        name: employeeCardId
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Employee
      - Cards
      - EmployeeCardId
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