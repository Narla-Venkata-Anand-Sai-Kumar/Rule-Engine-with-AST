# Rule Engine with AST

This project implements a simple three-tier rule engine application using **Flask**, **SQLAlchemy**, and **SQLite**. It enables the creation, combination, and evaluation of rules based on **Abstract Syntax Trees (ASTs)**.

## Overview

The application allows users to:

- **Create** individual rules using logical expressions.
- **Combine** multiple rules into composite rules.
- **Evaluate** rules against provided data inputs.
- **Modify** existing rules as needed.

## Setup

1. **Install Dependencies**:

   - Ensure you have Python installed on your system.
   - Install the required Python packages:

     ```
     pip install flask sqlalchemy requests
     ```

2. **Run the Backend Server**:

   - Start the Flask application to handle API requests:

     ```
     python main.py
     ```

3. **Run the Frontend Application (Optional)**:

   - Launch the Tkinter-based GUI for interacting with the backend:

     ```
     python rlg.py
     ```

## Components

1. **Backend** (`main.py`):

   - A Flask application providing RESTful API endpoints for rule operations.
   - Manages rule creation, combination, evaluation, and modification using a SQLite database.

2. **Frontend** (`rlg.py`):

   - A Tkinter-based graphical user interface.
   - Allows users to interact with the backend through a user-friendly interface.

3. **Automated Test Script** (`test.py`):

   - A script that automatically tests the application's functionality.
   - Interacts with the API endpoints to verify each feature.

## Application Features

- **Create Rule**:

  - Define new rules using logical expressions.
  - Each rule is assigned a unique ID upon creation.

- **Combine Rules**:

  - Merge multiple existing rules into a new composite rule.
  - Specify the IDs of the rules to be combined.

- **Evaluate Rule**:

  - Test a rule (individual or composite) against provided data inputs.
  - Receive a boolean result indicating whether the data satisfies the rule.

- **Modify Rule**:

  - Update an existing rule with a new logical expression.
  - Maintain the same rule ID for consistency.

## API Endpoints

1. **Create Rule** (`/create_rule`):

   - **Method**: `POST`
   - **Description**: Creates a new rule based on a provided logical expression.
   - **Parameters**: `rule_string` (the logical expression defining the rule).
   - **Response**: Rule ID and abstract syntax tree (AST) representation.

2. **Combine Rules** (`/combine_rules`):

   - **Method**: `POST`
   - **Description**: Combines specified rules into a composite rule.
   - **Parameters**: `rule_ids` (a list of rule IDs to combine).
   - **Response**: New composite rule ID and combined AST representation.

3. **Evaluate Rule** (`/evaluate_rule`):

   - **Method**: `POST`
   - **Description**: Evaluates a rule against provided data inputs.
   - **Parameters**: `rule_id` (ID of the rule to evaluate), `data` (a dictionary of data inputs).
   - **Response**: Evaluation result (`true` or `false`).

4. **Modify Rule** (`/modify_rule`):

   - **Method**: `POST`
   - **Description**: Modifies an existing rule with a new logical expression.
   - **Parameters**: `rule_id` (ID of the rule to modify), `new_rule_string` (the new logical expression).
   - **Response**: Confirmation message upon successful update.

## Sample Workflow

1. **Create Individual Rules**:

   - Define rules using logical expressions (e.g., age-based conditions, department checks).

2. **Combine Rules**:

   - Merge existing rules by specifying their IDs to form composite rules.

3. **Evaluate Rules**:

   - Provide data inputs to evaluate whether they satisfy the conditions of a rule.

4. **Modify Existing Rules**:

   - Update rules as requirements change without creating new IDs.

## Testing

- **Automated Testing**:

  - Use the `test.py` script to automate the testing of all functionalities.
  - The script tests rule creation, combination, evaluation, and modification.

  ```
  python test.py
  ```

- **Manual Testing**:

  - Use the Tkinter GUI (`rlg.py`) to interact with the application manually.
  - Alternatively, use tools like `curl` or `Postman` to send requests to the API endpoints.

## Summary

This rule engine application leverages the power of abstract syntax trees (ASTs) to parse and evaluate logical expressions efficiently. By providing a flexible framework for rule management, it enables users to define complex logic that can be easily modified and tested against various data inputs.

The professional design and minimalistic approach ensure that the application is both user-friendly and robust, suitable for integration into larger systems requiring dynamic rule evaluation.

---

**Note**: For any issues or further assistance, please refer to the project's documentation or contact the maintainers.