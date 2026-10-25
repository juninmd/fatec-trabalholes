```markdown
# AGENTS.md - Guidelines for AI Coding Agents

These guidelines are designed to ensure the development of high-quality, maintainable, and effective AI coding agents. Adherence to these principles is mandatory for all development activities.

## 1. DRY (Don't Repeat Yourself)

*   All code should have single, well-defined purposes.
*   Avoid duplicating logic and functionality.
*   Favor composition over inheritance whenever possible.
*   Modularize code into distinct, reusable components.

## 2. KISS (Keep It Simple, Stupid)

*   Strive for simplicity in design and implementation.
*   Prioritize readability and maintainability over complex solutions.
*   Avoid unnecessary abstractions or layers.
*   Keep functions and classes small and focused.

## 3. SOLID Principles

*   **Single Responsibility Principle:** Each class/function should have one and only one reason to change.
*   **Open/Closed Principle:** The system should be open for extension but closed for modification.
*   **Liskov Substitution Principle:** Subclasses must be able to replace all prior types.
*   **Interface Segregation Principle:** Clients should not be forced to depend on methods they do not use.
*   **Dependency Inversion Principle:** Interfaces should dictate implementation details.

## 4. YAGNI (You Aren't Gonna Need It)

*   Avoid implementing functionality that is not currently required.
*   Only implement features necessary for the current task.
*   Refactor code to remove unused components.

## 5. Code Style & Formatting

*   **Indentation:** Use 2 spaces for indentation.
*   **Line Length:** Max. 120 characters per line.
*   **Naming Conventions:** Follow established naming conventions (e.g., camelCase, snake_case).
*   **Comments:**  Provide concise, informative comments explaining *why* the code is doing something, not *what* it's doing.  Focus on logic and intent.
*   **Consistent Formatting:** Adhere to a single code style guide (e.g., Google Style).

## 6. File Size & Test Coverage

*   **Maximum File Size:** 180 lines of code total (excluding comments).
*   **Test Coverage:**  Minimum 80% coverage across all functions and classes. Automated tests will be implemented.
*   **Unit Tests:** All functions and classes will be thoroughly unit tested.
*   **Integration Tests:**  If applicable, integration tests will be conducted to verify system interactions.

## 7.  Development Workflow

1.  **Design:**  Conceptualize the solution and document high-level architecture.
2.  **Implement:** Write code, adhering to SOLID principles and best practices.
3.  **Test:** Write unit tests to cover core functionality.
4.  **Review:** Peer review code, ensuring correctness and adherence to standards.
5.  **Refactor:** Improve code structure, readability, and efficiency.
6.  **Refactor:**  Ensure code follows the style guide.
7.  **Repeat**

## 8.  Specific Considerations for AGENTS.md

*   **Agent Class Definition:**  Clearly define agent classes and their responsibilities.
*   **Communication Protocols:** Document the communication protocols used between agents.
*   **Data Structures:** Describe data structures used to manage agent states and data.
*   **Error Handling:** Implement robust error handling to prevent crashes and ensure data integrity.
*   **Logging:** Include informative logging to aid debugging and monitoring.

## 9.  Additional Guidelines

*   All code should be documented with clear and concise comments.
*   Consider security implications in all code.
*   Prioritize readability and maintainability.
*   Avoid unnecessary complexity.
*   Focus on correctness and performance.

These guidelines represent a minimum standard for development.  Any deviation from these principles requires careful consideration and justification.
```

<!-- base-actions-main-policy -->
## GitHub Actions — padrão obrigatório (@main)

- Referencie as actions internas sempre pelo branch, nunca por SHA:
  - `uses: juninmd/base-actions/<action>@main`
  - `uses: juninmd/base-actions/.github/workflows/<arquivo>.yml@main`
- Não fixe `@<sha>` em `juninmd/base-actions`: a atualização é centralizada no
  `main` e passa a valer no próximo run.
- PRs cujos checks não iniciam por billing/spending limit são mesclados pelo bot central
  `juninmd/base-actions/.github/workflows/auto-merge-billing-blocked.yml`.
  Para impedir o merge automático de um PR, aplique a label `do-not-merge`.