I’ve already completed the project, and now I want to go through the entire codebase systematically so I can understand what I built rather than just having a working project.

Could you help me create a **complete Swagger/OpenAPI documentation and a Postman API testing guide in Markdown (`.md`) format** based on the actual project?

### What I want

#### 1. Swagger / OpenAPI Documentation

Analyze the existing project and add Swagger/OpenAPI documentation to the APIs.

Please:

* Identify all controllers and REST endpoints.
* Document every endpoint with:

  * HTTP method
  * URL/path
  * Purpose/description
  * Path parameters
  * Query parameters
  * Request body
  * Required fields
  * Response structure
  * HTTP status codes
  * Possible error responses
* Add appropriate Swagger/OpenAPI annotations where they genuinely improve the documentation.
* Configure Swagger UI/OpenAPI correctly for the existing Spring Boot project.
* Do **not** change the business logic or unnecessarily refactor the project just for Swagger.
* Follow the existing project structure, naming conventions, and coding style.
* Make the minimum necessary code changes.

#### 2. Postman Guide

Create a detailed Markdown file, for example:

`POSTMAN_API_GUIDE.md`

The guide should allow me to test the project **endpoint by endpoint in a logical order**.

For every API, explain:

1. What this API does
2. Why we need to call it
3. HTTP method
4. URL
5. Headers
6. Authentication requirements, if applicable
7. Request body with a realistic example
8. Expected response
9. Expected HTTP status
10. What I should verify in the response/database
11. Which API I should call next

Organize the APIs into a proper workflow rather than simply listing them alphabetically.

For example:

```text
Step 1 → Create/Register User
Step 2 → Login / Obtain Token
Step 3 → Use Token for Authenticated APIs
Step 4 → Create Resource
Step 5 → Retrieve Resource
Step 6 → Update Resource
Step 7 → Partial Update
Step 8 → Delete Resource
Step 9 → Test validation/error scenarios
```

Adapt this flow to the **actual APIs and business logic present in my project** rather than assuming the project has these exact endpoints.

#### 3. Learning-Oriented Documentation

I don't just want documentation for testing purposes.

I want to use this as a way to **go through my project and understand it deeply**.

Therefore, wherever useful, explain:

* What happens when I call this endpoint?
* Which controller receives the request?
* Which service method is invoked?
* Which repository/database operation happens?
* What DTOs are involved?
* How the response is constructed?
* What validations are triggered?
* What exceptions can occur?
* How the request flows through the application?

Keep these explanations concise but technically accurate.

#### 4. Create a Patch File

Please also create a **patch/diff file** containing only the changes required to add Swagger/OpenAPI documentation.

For example:

`swagger-documentation.patch`

The patch should be based on the current project state and should contain only the Swagger-related changes.

I want to be able to review exactly what was changed before applying it.

### Important constraints

* **First inspect the existing project thoroughly.**
* Do not assume endpoint names, DTOs, request/response structures, authentication mechanisms, or database behavior.
* Base everything on the actual source code.
* Do not rewrite working code unnecessarily.
* Do not introduce unrelated improvements.
* Preserve the existing architecture and business logic.
* If something is already implemented correctly, don't modify it.
* If Swagger dependencies/configuration already exist, reuse them instead of duplicating them.
* Mention any assumptions clearly.
* If you find an issue unrelated to Swagger, document it separately rather than silently modifying it.

### Expected deliverables

Please provide:

```text
1. Swagger/OpenAPI implementation changes
2. SWAGGER_GUIDE.md
3. POSTMAN_API_GUIDE.md
4. swagger-documentation.patch
```

The final Markdown documentation should be written so that I can literally open it and **work through the APIs one by one in Postman while simultaneously reading the corresponding project code**.

The main goal is:

> **I want to use Swagger + Postman as a structured way to reverse-engineer and deeply understand the project I already built.**
