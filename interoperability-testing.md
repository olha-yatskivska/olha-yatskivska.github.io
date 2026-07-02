[Back to Main Page](./)

# Interoperability Testing 

> Sources:
> * Certified Tester Advanced Level Test Analyst (CTAL-TA) Syllabus
> * Course ISTQB Advanced Test Analyst from the [Trainer Alexandra Kovalova](https://certifiedunicorns.pro/advancedistqb?utm_source=telegram&utm_medium=webinar-agile-anons&utm_campaign=25-05)

Interoperability testing  is a sub-characteristic of Compatibility testing. 

## Compatibility (ISO 25010)

* Degree to which a product, system or component can exchange information with other products, systems or components, and/or perform its required functions while sharing the same common environment and resources.

* This characteristic is composed of the following sub-characteristics:
  * *Co-existence* - Degree to which a product can perform its required functions efficiently while sharing a common environment and resources with other products, without detrimental impact on any other product.
  * *Interoperability* - Degree to which a system, product or component can exchange information with other products and mutually use the information that has been exchanged.

## Interoperability Testing  (ISTQB)

* Interoperability testing verifies the exchange of information between two or more systems or components (API testing on Sandbox or Staging environment).
* Tests focus on the ability to exchange information and subsequently use the information that has been exchanged.
* Testing should cover all the intended target environments:
  * hardware
  * software
  * middleware (Enterprise Service Bus (ESBs), API Gateways, or Event Brokers (Apache Kafka))
  * operating system to ensure the data exchange will work properly. In reality, this may only be feasible for a relatively small number of environments.

* In that case interoperability testing may be limited to a selected representative group of environments.
* Specifying tests for interoperability requires that combinations of the intended target environments are identified, configured and available to the test team.
* These environments are then tested using a selection of functional suitability test cases which exercise the various data exchange points present in the environment.
* Interoperability relates to how different components and software systems interact with each other.
* Software with good interoperability characteristics can be integrated with a number of other systems without requiring major changes or significant impact on non-functional behaviour.
* The number of changes and the effort required to implement and test those changes may be used as a measure of interoperability.


## Testing for software interoperability may focus on the following design features:
   
 * Use of industry-wide communications standards, such as XML, JSON
 * Ability to automatically detect the communication needs of the systems it interacts with and adjust accordingly

## Interoperability testing may be particularly significant for the following:

 * Commercial off-the-shelf software products and tools
 * Applications based on a system of systems
 * Systems based on the Internet of Things
 * Webservices with connectivity to other systems


## Testing Levels

* This type of testing is performed during component integration and system integration testing.
* At the system integration level, this type of testing is conducted to determine how well the fully developed system interacts with other systems. Because systems may interoperate on multiple levels, the Test Analyst must understand these interactions and be able to create the conditions that will exercise the various interactions.

> Example: if two systems will exchange data, the Test Analyst must be able to create the necessary data and the transactions required to perform the data exchange.

## Testing Basis and Test Technigues

* It is important to remember that all interactions may not be clearly specified in the requirements documents.
* Instead, many of these interactions will be defined only in the system architecture and design documents.
* The Test Analyst must be able and prepared to examine these documents to determine the points of information exchange between systems and between the system and its environment to ensure all are tested.
* Techniques such as equivalence partitioning, boundary value analysis, decision tables, state transition diagrams, use cases and pairwise testing are all applicable to interoperability testing.
* Typical defects found include incorrect data exchange between interacting components.



Practice API

Validating Your Example: The "First Connection"
If your system connects to a partner’s live test endpoint (e.g., api.sandbox.paypal.com), authenticates successfully, sends a payload, and receives a valid response, you have just performed a basic interoperability test.

You have proven that:

The network firewalls allow the connection.
The SSL/TLS certificates are trusted by both sides.
The authentication (like an API key or OAuth token) works in a real environment.
However, a full interoperability test goes beyond just a successful ping. It tests a complete business workflow between the two live systems.

Here are three concrete examples of what API interoperability testing looks like in practice:

Example 1: Payment Gateway (e.g., Stripe or PayPal)
Imagine you are building an e-commerce app.

The Interoperability Test: You trigger a checkout in your Staging environment. Your system makes an API call to Stripe’s Sandbox environment using a test credit card number.
What makes it Interoperability Testing?
You aren't just checking if the JSON is formatted correctly (that's contract testing).
You are verifying that Stripe actually processes the test card, deducts the simulated funds, and sends a Webhook back to your system.
Finally, you verify that your system receives that Webhook, understands it, and updates the order status in your database to "Paid." Both systems worked together to complete a real-world transaction.


Example 2: "Log in with Google" (OAuth 2.0)
Imagine you are adding Single Sign-On (SSO) to your application.

The Interoperability Test: A tester clicks "Log in with Google" on your staging site. They are redirected to Google's actual login page, they enter their credentials, Google redirects them back to your site with an authorization code, and your backend API exchanges that code with Google for an access token.
What makes it Interoperability Testing?
It involves a complex, multi-step dance between a web browser, your backend, and Google's live servers. If Google changes how their redirect URIs work, or if your server's clock is out of sync with Google's (causing token validation to fail), this test will catch it. Contract testing would miss those environmental issues.
Example 3: Travel Booking (Standardized APIs)
Imagine a travel agency app that connects to an airline's API to book a flight.

The Interoperability Test: Your system sends an API request to the airline's test environment to book a seat for "John Doe."
What makes it Interoperability Testing?
You are testing Semantic Interoperability (meaning). Does the airline's system actually reserve the seat in their database? If you immediately send a second API request to check seat availability, does the airline's API now show that seat as "Unavailable"?
You are proving that the data you sent actually changed the state of the airline's system in the way you expected.
Summary: The Checklist for an API Interoperability Test
To know if you are doing an interoperability test, ask yourself:

Are both systems "alive"? (No mocks, no stubs. You are talking to a real Sandbox, Staging, or Production environment).
Are we testing a business goal? (e.g., Booking a ticket, processing a payment, syncing user data).
Did the state change? (e.g., Was a database updated, an email sent, or a file generated on the other side?).
