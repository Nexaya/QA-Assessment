#### **JavaScript (`automation/javascript/README.md`):**

```markdown
# JavaScript Automation Instructions

## Task:
- Write an automated test script using **JavaScript** to test the login functionality of a web-based application.
- Ensure that both valid and invalid login scenarios are covered.

## Requirements:
- Use **Cypress** or **Selenium** with **JavaScript** to automate the test.
- Ensure to include assertions for success and failure scenarios.

## Deliverables:
- Submit your JavaScript code along with instructions to run the test.
- Include a `package.json` file if using Node.js or npm.

---

## Sample:
```javascript
describe('Login Test', () => {
  it('should log in successfully with valid credentials', () => {
    cy.visit('http://example.com/login');
    cy.get('input[name="username"]').type('valid_username');
    cy.get('input[name="password"]').type('valid_password');
    cy.get('button[type="submit"]').click();
    cy.title().should('include', 'Dashboard');
  });

  it('should show an error message for invalid credentials', () => {
    cy.visit('http://example.com/login');
    cy.get('input[name="username"]').type('invalid_username');
    cy.get('input[name="password"]').type('invalid_password');
    cy.get('button[type="submit"]').click();
    cy.contains('Invalid credentials').should('be.visible');
  });
});
