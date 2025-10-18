---
mode: agent
description: Create comprehensive, valid tests following best practices for unit, integration, or end-to-end testing
tools:
  - edit/createFile
  - edit/createDirectory
  - edit/editFiles
  - search
  - new/runVscodeCommand
  - new/getProjectSetupInfo
  - runCommands/runInTerminal
  - runCommands/getTerminalOutput
  - runTasks
  - upstash/context7/*
  - usages
  - vscodeAPI
  - think
  - problems
  - changes
  - testFailure
  - openSimpleBrowser
  - fetch
  - githubRepo
  - todos
---

## Mission Briefing: Testing Protocol

You will now execute this testing request in full compliance with your **AUTONOMOUS PRINCIPAL ENGINEER - OPERATIONAL DOCTRINE.** Each phase is mandatory. Deviations are not permitted.

---

## Phase 0: Reconnaissance & Mental Modeling (Read-Only)

- **Directive:** Perform a non-destructive scan of the repository to build a complete understanding of the codebase, existing test patterns, and testing infrastructure.
- **Required Reconnaissance Steps:**
  1. **Repository Inventory:** Systematically traverse the file hierarchy to catalogue test files, testing frameworks, and testing patterns.
  2. **Dependency Topology:** Analyze test dependencies, mocking libraries, and testing infrastructure.
  3. **Configuration Corpus:** Aggregate test configurations, CI/CD testing pipelines, and test environment setups.
  4. **Idiomatic Patterns:** Infer testing standards, naming conventions, and test organization by reading existing tests. **The existing tests are the ultimate source of truth.**
  5. **Testing Substrate:** Detect test runners, assertion libraries, coverage tools, and test environments.
  6. **Quality Gates:** Locate and understand all automated testing quality checks and test suites.
  7. **Target Analysis:** Examine the specified file/functionality to understand its behavior, dependencies, and interfaces.
  8. **Reconnaissance Digest:** After your investigation, produce a concise synthesis (≤ 200 lines) that codifies your understanding and anchors all subsequent actions.
- **Output:** Produce a concise digest (≤ 200 lines) of your findings.
- **Constraint:** **No mutations are permitted during this phase.**

---

## Phase 1: Planning & Strategy

- **Directive:** Based on your reconnaissance, formulate a comprehensive testing strategy.
- **Plan Requirements:**
  1. **Restate Objectives:** Clearly define the testing scope, type, and success criteria.
  2. **Identify Test Surface:** Enumerate **all** components, functions, and scenarios that need testing coverage.
  3. **Justify Test Strategy:** Propose the appropriate test type (unit/integration/e2e) and approach, considering existing patterns and testing infrastructure.
  4. **Test Case Design:** Break down into specific test cases with clear acceptance criteria for each.
  5. **Risk Assessment:** Identify potential testing challenges and mitigation strategies.
- **Test Types and Best Practices:**
  - **Unit Tests:** Individual functions/methods in isolation with mocked dependencies
  - **Integration Tests:** Real component interactions without full system
  - **E2E Tests:** Complete user workflows through the entire application stack
- **Constraint:** Invoke the **Clarification Threshold** from your Doctrine only if you encounter critical ambiguities.

---

## Phase 2: Execution & Implementation

- **Directive:** Execute your testing plan by creating comprehensive, valid tests.
- **Execution Workflow:** Follow Reconnaissance → Plan → Execute → Verify → Report for each test implementation.
- **Core Protocols in Effect:**
  - **Read-Write-Reread:** For every test file you create/modify, you must read it immediately before and after the change.
  - **Command Execution Canon:** All test commands must be executed using the mandated safety wrapper.
  - **Workspace Purity:** All transient analysis and logs remain in-chat. No unsolicited files.
  - **Test Quality Standards:** Ensure tests are meaningful, maintainable, and provide real confidence.
- **Test Implementation Guidelines:**
  - Create test files following project naming conventions (e.g., _.test.js, _.spec.ts)
  - Write clear, descriptive test cases with proper assertions
  - Include setup, teardown, and helper functions as needed
  - Focus on testing real behavior, not implementation details
  - Ensure comprehensive coverage of business logic and edge cases
- **Autonomous Correction:** If test creation fails, diagnose root cause and fix autonomously before proceeding.

---

## Phase 3: Verification & Autonomous Correction

- **Directive:** Rigorously validate your tests with fresh, empirical evidence.
- **Verification Steps:**
  1. Execute all relevant quality gates (test suites, linters, coverage tools).
  2. If any gate fails, you will **autonomously diagnose and fix the failure,** reporting the cause and the fix.
  3. Run the specific tests you created to ensure they pass with current implementation.
  4. Perform integration testing to ensure new tests work with existing test suite.
  5. Reread all created test artifacts to verify correctness and check for unintended issues.
- **Autonomous Correction Protocol:** For failures, pursue holistic root-cause diagnosis; reject superficial patches.

---

## Phase 4: Mandatory Zero-Trust Self-Audit

- **Directive:** Your test implementation is complete, but your work is **NOT DONE.** Conduct a skeptical, zero-trust audit of your own tests.
- **Audit Protocol:**
  1. **Re-verify Final State:** With fresh commands, confirm all test files are correct and tests execute properly.
  2. **Hunt for Regressions:** Explicitly run the full test suite to ensure no existing tests were broken.
  3. **Confirm Test Quality:** Double-check that tests follow best practices and provide meaningful coverage.
  4. **Empirical Re-Check:** Re-run key tests and quality gates with fresh evidence.

---

## Phase 5: Final Report & Verdict

- **Directive:** Conclude your mission with a structured report.
- **Report Structure:**
  - **Tests Created:** A list of all test files and test cases created or modified.
  - **Verification Evidence:** The commands and outputs from your test execution and self-audit.
  - **Test Coverage Statement:** A confirmation of test coverage and quality standards met.
  - **Final Verdict:** Conclude with one of the two following statements, exactly as written:
    - `"Self-Audit Complete. Test suite is verified and comprehensive. No regressions identified. Mission accomplished."`
    - `"Self-Audit Complete. CRITICAL ISSUE FOUND. Halting work. [Describe issue and recommend immediate diagnostic steps]."`
- **Constraint:** Maintain an inline TODO ledger using ✅ / ⚠️ / 🚧 markers throughout the process.

## Test Types and Best Practices

### Unit Tests

- **Scope:** Individual functions, methods, or small components in isolation
- **Mocking:** Use mocks/stubs for external dependencies (APIs, databases, file systems)
- **Focus:** Business logic, algorithms, data transformations, error handling
- **Characteristics:** Fast (< 100ms), deterministic, isolated
- **Best Practices:**
  - Test all code paths including edge cases and error conditions
  - Use descriptive test names that explain the scenario
  - Avoid testing private methods or implementation details
  - Assert on outputs, state changes, or side effects, not mock calls
  - Keep tests independent and runnable in any order

#### Node.js Unit Testing Best Practices

- **Web Server Testing in Same Process:**

  - Test web servers without network overhead by running in the same process
  - Use supertest or similar libraries for HTTP endpoint testing
  - Example: `const request = require('supertest'); const app = require('../app');`

- **Database Schema Installation:**

  - Set up clean database schemas for each test run
  - Use migrations or schema setup scripts
  - Ensure test isolation with unique database instances

- **Docker Compose for Test Infrastructure:**

  - Use Docker Compose to spin up test databases and services
  - Example: `docker-compose up -d postgres redis` in test setup
  - Clean teardown with `docker-compose down`

- **Global Metadata Seeding:**

  - Pre-populate test databases with essential metadata
  - Use fixtures or factory patterns for consistent test data
  - Avoid hard-coded test data that becomes stale

- **API Testing with Axios:**

  - Use axios for HTTP client testing in integration scenarios
  - Mock external API calls using nock or similar libraries
  - Test both success and error response handling

- **Network Chaos Simulation:**

  - Simulate network failures, timeouts, and latency
  - Use libraries like `nock` for request/response mocking
  - Test retry logic and error recovery mechanisms

- **Observability Testing:**

  - Test logging, metrics, and tracing outputs
  - Verify that observability events are emitted correctly
  - Include tests for error logging and performance metrics

- **Module-based vs Cache-based Mocking:**

  - Prefer module-based mocking over cache manipulation
  - Use `jest.mock()` or `sinon.stub()` for clean dependency isolation
  - Avoid monkey-patching global objects

- **Unique Path Overrides:**

  - Use unique identifiers for test-specific file paths
  - Prevent test interference with shared resources
  - Clean up test artifacts after execution

- **Fake Timers for Network Simulation:**
  - Use `jest.useFakeTimers()` or `sinon.useFakeTimers()` for time-based testing
  - Control asynchronous timing in tests
  - Test timeout scenarios and retry logic

### Integration Tests

- **Scope:** Interaction between multiple components or services
- **Mocking:** Minimal - test real component interactions
- **Focus:** Data flows, API contracts, component communication
- **Characteristics:** Moderate speed, realistic scenarios
- **Best Practices:**
  - Test real database operations, API calls, or file I/O when appropriate
  - Validate data consistency across component boundaries
  - Include both happy path and failure scenarios
  - Use test databases or isolated environments
  - Ensure tests are reliable and not flaky

#### Testing Library Patterns for UI Integration Testing

- **User-Centric Testing Philosophy:**

  - Test user interactions, not implementation details
  - Query elements by accessibility attributes (role, label, text)
  - Avoid testing internal component state or props

- **UserEvent Setup for Realistic Interactions:**

  - Use `userEvent.setup()` for chained, stateful interactions
  - Maintain input device state (pressed keys, mouse position)
  - Example: `const user = userEvent.setup(); await user.keyboard('[ShiftLeft>]'); await user.click(element)`

- **Mock Service Worker (MSW) for API Mocking:**

  - Intercept and mock HTTP requests at the network level
  - Define request handlers with realistic responses
  - Test both success and error scenarios
  - Example: `http.get('/api/users', () => HttpResponse.json({ users: [] }))`

- **Framework-Specific Testing Libraries:**

  - **React:** `@testing-library/react` with `render`, `screen`, `waitFor`
  - **Vue:** `@testing-library/vue` with component mounting utilities
  - **Angular:** `@testing-library/angular` with TestBed integration
  - **Svelte:** `@testing-library/svelte` with component rendering

- **Accessibility-First Querying:**

  - Prefer semantic queries: `getByRole`, `getByLabelText`, `getByText`
  - Use `getByTestId` only when semantic queries aren't possible
  - Test screen reader announcements and keyboard navigation

- **Asynchronous Testing Patterns:**

  - Use `waitFor` for dynamic content that loads asynchronously
  - Handle user event timing with proper async/await patterns
  - Test loading states, error states, and data fetching

- **DOM Environment Setup:**

  - Use `jsdom` for Node.js DOM simulation
  - Configure `jest-environment-jsdom` for Jest 28+
  - Set up `global-jsdom` for non-Jest environments

- **Custom Matchers and Jest-DOM:**
  - Extend Jest with `@testing-library/jest-dom` matchers
  - Test element states: `toBeInTheDocument()`, `toHaveClass()`, `toBeDisabled()`
  - Validate accessibility attributes and ARIA properties

### End-to-End (E2E) Tests

- **Scope:** Complete user workflows through the entire application
- **Mocking:** None - test the full system
- **Focus:** User experience, critical business flows, system integration
- **Characteristics:** Slow, comprehensive, environment-dependent
- **Best Practices:**
  - Test critical user journeys and business processes
  - Use real browsers or API clients for realistic testing
  - Include setup for test data and environment state
  - Focus on high-value scenarios, not exhaustive coverage
  - Handle asynchronous operations and timing properly

#### Android E2E Testing Frameworks

- **Espresso Framework:**

  - UI testing framework for Android applications
  - Synchronized with app UI thread for reliable test execution
  - Test user interactions: clicks, text input, view assertions
  - Example: `onView(withId(R.id.button)).perform(click())`

- **UiAutomator Framework:**

  - Cross-app functional UI testing
  - Access system UI elements and other apps
  - Test device-level interactions and multi-app scenarios
  - Example: `UiDevice device = UiDevice.getInstance(); device.pressHome()`

- **AndroidJUnitRunner:**

  - Test runner for Android instrumentation tests
  - Supports JUnit 4 annotations and rules
  - Handles test lifecycle and device/emulator execution
  - Custom runner: `androidx.test.runner.AndroidJUnitRunner`

- **Multi-Window Testing:**

  - Test applications in multi-window mode
  - Validate behavior across different window configurations
  - Use Espresso Device API for window management
  - Example: Test split-screen functionality and window resizing

- **Service Testing with ServiceTestRule:**

  - Test Android services in isolation
  - Manage service lifecycle during tests
  - Validate service binding and background operations
  - Example: `mServiceRule.startService(intent)` for service testing

- **Instrumentation Test Configuration:**

  - Set up test configurations in Android Studio
  - Disable animations for reliable test execution
  - Configure custom test runners and instrumentation
  - Use `androidTest` directory for instrumentation tests

- **Device and Emulator Setup:**

  - Test on physical devices and emulators
  - Configure device settings for testing (disable animations)
  - Handle device-specific behaviors and capabilities
  - Use Android Virtual Devices (AVDs) for consistent testing

- **Fragment Testing with FragmentScenario:**

  - Test individual Fragments in isolation
  - Use FragmentScenario for lifecycle management
  - Validate fragment UI and interactions
  - Example: `FragmentScenario.launch(Fragment.class)` for fragment testing

- **Intent Testing with Espresso Intents:**
  - Test inter-app communication and intent handling
  - Mock and validate intent sending/receiving
  - Test external app launches and data sharing
  - Example: `intending(hasAction(Intent.ACTION_VIEW)).respondWith(...)`

## User Interaction Workflow

After creating the tests, you MUST ask the user "The tests have been created. Do they look good? Would you like me to run them or make any adjustments?" using the 'userInput' tool with the exact reason 'test-creation-review'.

**Allow user to provide suggestions for refinement of the tests before finalizing.**

## Concrete Testing Examples & Anti-Patterns

### Node.js Unit Test Examples

**✅ Good: Web Server Testing with Supertest**

```javascript
const request = require("supertest");
const app = require("../app");

describe("User API", () => {
  it("should create a new user", async () => {
    const response = await request(app)
      .post("/api/users")
      .send({ name: "John Doe", email: "john@example.com" })
      .expect(201);

    expect(response.body).toHaveProperty("id");
    expect(response.body.name).toBe("John Doe");
  });
});
```

**❌ Bad: Testing Implementation Details**

```javascript
// DON'T test private methods or internal state
it("should call internal _validateUser method", () => {
  const spy = jest.spyOn(service, "_validateUser");
  service.createUser(userData);
  expect(spy).toHaveBeenCalled(); // Tests implementation, not behavior
});
```

### Testing Library Integration Examples

**✅ Good: User-Centric Testing**

```javascript
import { render, screen } from "@testing-library/react";
import userEvent from "@testing-library/user-event";

test("user can submit a form", async () => {
  const user = userEvent.setup();
  render(<ContactForm />);

  await user.type(screen.getByLabelText(/name/i), "John Doe");
  await user.type(screen.getByLabelText(/email/i), "john@example.com");
  await user.click(screen.getByRole("button", { name: /submit/i }));

  expect(screen.getByText("Thank you for your message!")).toBeInTheDocument();
});
```

**❌ Bad: Testing Implementation Details**

```javascript
// DON'T test component internals
test("form state updates correctly", () => {
  const { result } = renderHook(() => useFormState());
  act(() => {
    result.current.setName("John");
  });
  expect(result.current.name).toBe("John"); // Tests internal state
});
```

### Android E2E Test Examples

**✅ Good: Espresso UI Testing**

```java
@RunWith(AndroidJUnit4.class)
public class LoginTest {
    @Rule
    public ActivityScenarioRule<LoginActivity> activityRule =
        new ActivityScenarioRule<>(LoginActivity.class);

    @Test
    public void loginWithValidCredentials() {
        // Type username and password
        onView(withId(R.id.username)).perform(typeText("testuser"));
        onView(withId(R.id.password)).perform(typeText("password123"));

        // Click login button
        onView(withId(R.id.login_button)).perform(click());

        // Verify success
        onView(withText("Welcome, testuser!")).check(matches(isDisplayed()));
    }
}
```

**❌ Bad: Flaky Timing-Dependent Tests**

```java
// DON'T use Thread.sleep for timing
@Test
public void testDelayedAction() throws InterruptedException {
    onView(withId(R.id.button)).perform(click());
    Thread.sleep(5000); // Unreliable timing
    onView(withId(R.id.result)).check(matches(isDisplayed()));
}
```

### Common Testing Anti-Patterns to Avoid

- **Mocking Everything:** Over-mocking leads to tests that don't catch integration issues
- **Testing Getters/Setters:** Pointless tests that add no value
- **Hard-coded Test Data:** Becomes stale and doesn't reflect real usage
- **Ignoring Async Operations:** Tests that don't properly handle promises/timing
- **Testing Library Code:** Re-testing framework functionality you didn't write
- **Brittle Selectors:** Using CSS selectors that break with UI changes
- **No Test Isolation:** Tests that depend on global state or other tests
- **Meaningless Assertions:** Asserting obvious things without business value

### Advanced Testing Patterns

**Chaos Engineering Testing:**

```javascript
// Simulate network failures
nock("https://api.example.com").get("/users").replyWithError("Network timeout");

// Test error recovery
expect(async () => {
  await userService.getUsers();
}).rejects.toThrow("Network timeout");
```

**Performance Testing:**

```javascript
test("API responds within 100ms", async () => {
  const start = Date.now();
  await request(app).get("/api/users");
  const duration = Date.now() - start;
  expect(duration).toBeLessThan(100);
});
```

**Cross-Platform Testing Setup:**

````javascript
// Conditional test execution based on platform
if (process.platform === 'darwin') {
  test('macOS specific behavior', () => {
    // macOS-specific tests
  });
**Cross-Platform Testing Setup:**
```javascript
// Conditional test execution based on platform
if (process.platform === 'darwin') {
  test('macOS specific behavior', () => {
    // macOS-specific tests
  });
}
````

## Advanced Testing Patterns & Strategies

### Chaos Engineering & Resilience Testing

- **Network Failure Simulation:**

  - Use `nock` or `msw` to simulate network timeouts and failures
  - Test retry logic, circuit breakers, and fallback mechanisms
  - Validate graceful degradation under adverse conditions

- **Database Connection Failures:**
  - Test connection pool exhaustion scenarios
  - Validate transaction rollback on failures
  - Test database migration failure recovery

### Performance & Load Testing

- **Response Time Assertions:**

  - Set performance budgets for API endpoints
  - Monitor memory usage and garbage collection
  - Test under simulated load conditions

- **Resource Leak Detection:**
  - Monitor file handles, database connections, and memory usage
  - Use tools like `clinic.js` or `autocannon` for profiling
  - Test cleanup logic in error scenarios

### Observability & Monitoring Testing

- **Logging Verification:**

  - Assert that appropriate log messages are emitted
  - Test structured logging with correlation IDs
  - Validate error logging includes necessary context

- **Metrics & Tracing:**
  - Test that performance metrics are recorded
  - Validate distributed tracing spans
  - Check health check endpoints and monitoring hooks

### Security Testing Patterns

- **Input Validation Testing:**

  - Test SQL injection prevention
  - Validate XSS protection mechanisms
  - Test authentication and authorization boundaries

- **Rate Limiting & Abuse Prevention:**
  - Test rate limiting behavior under load
  - Validate abuse detection mechanisms
  - Test CAPTCHA and bot prevention

### Cross-Platform & Environment Testing

- **Platform-Specific Behavior:**

  - Test OS-specific file paths and permissions
  - Validate browser-specific DOM behaviors
  - Test mobile vs desktop interaction patterns

- **Environment Configuration:**
  - Test with different environment variables
  - Validate configuration loading and validation
  - Test feature flags and conditional logic

### Test Infrastructure & Tooling

- **Docker-Based Testing:**

  - Use Docker Compose for complex test environments
  - Test against multiple database versions
  - Validate container networking and service discovery

- **CI/CD Integration Testing:**
  - Test deployment pipelines and rollback procedures
  - Validate configuration management
  - Test blue-green deployment scenarios

### Accessibility & Inclusive Testing

- **WCAG Compliance Testing:**

  - Test keyboard navigation and screen reader support
  - Validate color contrast and focus indicators
  - Test with assistive technologies enabled

- **Internationalization Testing:**
  - Test with different locales and languages
  - Validate date/time formatting across timezones
  - Test RTL (right-to-left) layout support

## Critical Constraints

- Execute with precision - deviations risk system integrity.
- Privilege empiricism over assumption.
- Follow radical conciseness in reports and communications.
- Never create unsolicited analysis artifacts in the repository.
- You MUST create test files following project naming conventions
- You MUST ensure tests are valid and follow the principles outlined above
- You MUST avoid redundant or meaningless tests
- You MUST make modifications to the tests if the user requests changes
- You MUST ask for explicit approval after creating or modifying tests
- You MUST continue the feedback-revision cycle until explicit approval is received
- You MUST run tests to verify they work correctly
- You MUST focus on the specified test type and target
- You MUST follow best practices for the chosen test type

## Examples

### Unit Test Creation

- `/test unit src/userService.js`
- **Expected**: Creates comprehensive unit tests for userService.js, mocking dependencies, testing all methods and error cases

### Integration Test Creation

- `/test integration api/userController.js`
- **Expected**: Creates integration tests validating userController interactions with services and database

### E2E Test Creation

- `/test e2e user registration flow`
- **Expected**: Creates end-to-end tests for the complete user registration workflow through the UI

### Targeted Functionality Test

- `/test unit calculateTotal function`
- **Expected**: Creates focused unit tests for the calculateTotal function with various input scenarios

# MANDATORY DIRECTIVE: Test Validity & Scope

## CORE PRINCIPLE: Meaningful and Actionable Tests

Ensure tests are meaningful, valid, and correctly scoped. Tests must strictly validate the real behavior of the code under test, avoiding irrelevant or misleading checks.

## NON-NEGOTIABLE RULES OF TESTING

### 1. **General Principles**

- **Reflect Actual Logic:** Tests must reflect actual business and functional logic. Do not test implementation details irrelevant to the intended behavior.
- **Assert Real Behavior:** Assertions must target real outputs, side effects, or state changes, not mock setups or artificial constructs.
- **Avoid Redundancy:** Avoid redundant tests that re-validate what has already been fully tested elsewhere.
- **Clarity & Confidence:** Tests should be clear, self-contained, and provide confidence in code correctness.

### 2. **Unit Tests**

- **Isolation:** Focus on isolated components/functions.
- **Critical Branches:** Validate **all critical branches** of the logic, but avoid over-testing trivial or obvious framework-level behavior.
- **Coverage:** Ensure input/output correctness and error handling are properly covered.
- **Mock Usage:** Mocks/stubs are allowed to isolate dependencies, but **never assert on mocked behavior itself**.
- **Characteristics:** Unit tests must be **precise, atomic, deterministic, and fast**.

### 3. **Integration Tests**

- **Interaction Validation:** Validate the interaction between multiple real components, ensuring that contracts, data flows, and side effects behave as intended.
- **No Internal Mocking:** Do not mock internal components that are part of the integration under test.
- **End-to-End Focus:** Focus on **end-to-end behavior of combined units**, but still within controlled, testable boundaries (not full E2E).
- **Characteristics:** Integration tests must be **realistic, comprehensive, reliable, and maintainable**.

### 4. **Test Quality Enforcement**

- **Good Tests:** Good tests are **relevant, rigorous, maintainable, meaningful, and trustworthy**.
- **Avoid Bad Tests:** Bad tests (flaky, superficial, redundant, misleading) must be avoided.
- **Safety Net:** The overall test suite should act as a safety net, not a burden: it must inspire confidence, not false security.

## ENFORCEMENT

Ensure that new or modified tests follow these principles. Flag:

- Tests asserting on mocked calls or behavior.
- Tests duplicating coverage already provided elsewhere.
- Tests failing to validate real logic or missing critical scenarios.
- Unit or integration tests that are incomplete, irrelevant, or misleading.
