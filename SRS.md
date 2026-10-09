CABGO – CAB BOOKING APPLICATION

Software Requirements Specification (SRS)

Document Attributes

Attribute| Details
Document ID| CABGO-SRS-001
Version| 1.0
Status| Draft
Prepared For| CABGO Project
Project Team| Elite Six
Technology Baseline| HTML, CSS, JavaScript
Classification| Academic Project
Date| 09 October 2026

Table of Contents

1. Introduction
2. Business Context and Objectives
3. Stakeholders and User Classes
4. Product Overview and System Context
5. Assumptions, Constraints and Dependencies
6. Functional Requirements
7. Business Rules
8. Use Case Specifications
9. Data Requirements
10. External Interface Requirements
11. Non-Functional Requirements
12. Security and Access Control
13. Error Handling and Validation
14. Acceptance and Release Criteria
15. Requirements Traceability Matrix
16. Out of Scope / Future Considerations
17. Conclusion
18. References

1. Introduction

CABGO is a cab booking application designed to make ride booking convenient and user-friendly. It allows customers to enter pickup and drop locations, select a cab, view the estimated fare, confirm bookings and check booking history.

Purpose: This document defines the functional and non-functional requirements of CABGO and serves as a guide for its design, development and testing.

Scope: The initial version focuses on the basic cab booking process.

2. Business Context and Objectives

Business Context

Customers need a convenient way to arrange transportation without manually searching for cab services. CABGO aims to simplify this process through an application.

Objectives

- Provide a simple cab booking process.
- Allow users to enter pickup and drop locations.
- Display estimated fares before booking.
- Confirm valid ride bookings.
- Allow customers to view booking history.

3. Stakeholders and User Classes

Stakeholder| Role
Customer| Registers, selects a cab and books rides
Driver| Provides the cab service
Administrator| Manages users and booking information
Development Team| Designs, develops and tests the application

4. Product Overview and System Context

CABGO is intended to operate as a user-friendly cab booking application.

Main Modules

1. User registration and login
2. Pickup and drop location entry
3. Cab selection
4. Fare estimation
5. Booking confirmation
6. Booking history

System Context

The customer interacts with the application through its user interface. The application validates trip details, calculates an estimated fare and records the booking. Driver management, GPS tracking and payment integration may require additional services in future versions.

5. Assumptions, Constraints and Dependencies

Assumptions

- Users have access to a compatible device.
- Users enter valid information.
- Cab availability information is provided by the system.

Constraints

- The initial version focuses on basic booking functions.
- The system requires a suitable development environment.
- GPS tracking and online payments are outside the initial scope.

Dependencies

- A web browser for accessing the application.
- A database or suitable storage mechanism if persistent records are implemented.
- An internet connection for online deployment.

6. Functional Requirements

FR01 – User Registration and Login: The system shall allow users to register and log in using valid credentials.

FR02 – Location Entry: The system shall allow customers to enter pickup and drop locations.

FR03 – Cab Selection: The system shall allow customers to select an available cab.

FR04 – Fare Estimation: The system shall calculate and display an estimated fare based on trip details and the configured fare rules.

FR05 – Booking and History: The system shall confirm valid bookings and allow customers to view their booking history.

7. Business Rules

1. Pickup and drop locations are mandatory.
2. Pickup and drop locations must be valid and different.
3. A cab can be selected only if it is available.
4. The estimated fare must be displayed before booking confirmation.
5. A booking must contain all required trip details.
6. The system must display a confirmation message after a successful booking.

8. Use Case Specifications

Use Case: Book a Cab

Use Case ID: UC01

Primary Actor: Customer

Precondition: The application is accessible, and the customer has opened the booking page.

Main Flow:

1. The customer logs in if authentication is required.
2. The customer enters pickup and drop locations.
3. The system validates the locations.
4. The customer selects an available cab.
5. The system calculates and displays the estimated fare.
6. The customer confirms the booking.
7. The system records the booking and displays confirmation.

Alternative Flow:

- If a location is missing, the system displays a validation message.
- If no cab is available, the system informs the customer.
- If the details are invalid, the system requests correction.

Postcondition: A successful booking is recorded and available for viewing.

9. Data Requirements

The system may maintain the following information:

Data Entity| Attributes
User| User ID, Name, Email, Password Hash, Role
Cab| Cab ID, Cab Type, Availability Status
Booking| Booking ID, User ID, Pickup, Drop, Fare, Status
Driver| Driver ID, Name, Contact, Availability

Sensitive information must be handled securely. Passwords should be stored as secure hashes rather than plain text.

10. External Interface Requirements

User Interface

- Registration and login forms
- Pickup and drop input fields
- Cab selection interface
- Fare display
- Booking confirmation page
- Booking history page

Software Interface

The application may use a database or storage service to maintain user and booking records.

Hardware Interface

The application should be accessible from compatible computers and smartphones.

Communication Interface

A deployed online version requires network connectivity to communicate with its server and any integrated services.

11. Non-Functional Requirements

NFR01 – Performance: The application should respond to user actions within 3 seconds under normal operating conditions.

NFR02 – Security: User credentials and personal information must be protected against unauthorized access.

NFR03 – Usability: The application should provide a clear, simple and user-friendly interface.

NFR04 – Reliability: The system should process valid bookings correctly and prevent duplicate bookings from repeated submissions.

NFR05 – Availability: The deployed application should target 99% availability, excluding scheduled maintenance.

12. Security and Access Control

- Authentication must be implemented before protected account features are accessed.
- Customers should access only their permitted account and booking information.
- Administrative functions should be restricted to authorized administrators.
- Passwords must be securely hashed if password authentication is implemented.
- User inputs must be validated to reduce security risks.
- Sensitive information must not be exposed in error messages.

13. Error Handling and Validation

The system shall handle the following situations:

1. Empty pickup or drop location: display a validation message.
2. Invalid login details: display an authentication error.
3. No available cab: display an availability message.
4. Invalid booking details: prevent booking submission.
5. Fare calculation failure: display an error and allow retrying.
6. Storage or server failure: display an appropriate message without falsely confirming the booking.

Test Cases

ID| Test Scenario| Expected Result
TC01| Register with valid details| Account created successfully
TC02| Log in with valid credentials| Login successful
TC03| Log in with invalid credentials| Error message displayed
TC04| Enter valid pickup and drop locations| Locations accepted
TC05| Leave pickup location empty| Validation message displayed
TC06| Select an available cab| Cab selected successfully
TC07| Calculate fare for valid trip details| Estimated fare displayed
TC08| Confirm a valid booking| Booking confirmation displayed
TC09| View booking history| Previous bookings displayed
TC10| Submit booking with missing required details| Booking rejected with validation message

Test Execution Results

All test cases must be executed after the relevant features are implemented. Record the actual result and mark each case Pass or Fail. Until then, the status remains Pending.

14. Acceptance and Release Criteria

The application may be considered ready for release when:

- All five functional requirements are implemented.
- Valid and invalid inputs are handled correctly.
- Fare estimation follows the configured fare rules.
- Valid bookings are confirmed and recorded.
- Booking history displays the correct records.
- Security and access controls are tested.
- All ten test cases have documented execution results.
- Critical defects are resolved before release.

15. Requirements Traceability Matrix

Requirement ID| Requirement| Related Test Cases
FR01| Registration and login| TC01, TC02, TC03
FR02| Location entry| TC04, TC05
FR03| Cab selection| TC06
FR04| Fare estimation| TC07
FR05| Booking and history| TC08, TC09, TC10
NFR01| Performance| Performance testing
NFR02| Security| Security testing
NFR03| Usability| Usability testing
NFR04| Reliability| Booking reliability testing
NFR05| Availability| Availability testing

16. Out of Scope / Future Considerations

The following features are not included in the initial version but may be developed later:

- GPS-based live tracking
- Online payment integration
- Live driver location
- Ride cancellation
- Customer ratings and feedback
- Notifications and booking alerts

17. Conclusion

CABGO aims to simplify cab booking through a convenient and user-friendly application. This SRS defines the system requirements, business rules, interfaces, security considerations and testing expectations. It provides a foundation for implementation and future enhancement by Team Elite Six.
