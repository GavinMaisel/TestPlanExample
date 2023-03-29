# Test Plan Example
- Tests are written in Gherkin (Given/When/Then) format
- Test scenarios can be automated
- Tests can also serve as a Product Catalog of existing business functionality


## Login UI Tests

### Login_Success_Desktop
    
    Given I am an existing user who is logged out on desktop
    
    When I log in
    
    Then I am logged in

### Login_Success_for_Mobile_Web
    
    Given I am an existing user who is logged out on mobile web
    
    When I log in on mobile view
    
    Then I am logged in on mobile view

### Unable_to_Login_with_Non-Existent_Email
    
    Given I am a guest on the login page
    
    When I try to log in with a non-existent email address
    
    Then I see the error invalid username/password

### Unable_to_Login_with_Incorrect_Password
    
    Given I am a guest on the login page
    
    When I try to log in with an incorrect password
    
    Then I see the error invalid username/password

### Unable_to_Login_with_Invalid_Email_Address_Format
    
    Given I am a guest on the login page
    
    When I enter an invalid email
    
    Then I see an error for invalid email
    
    
## GraphQL Schema Tests

### GraphQL: schema

  Given I am a user
  
  And I want to query the schema
  
  When I hit the GraphQL API
  
  Then I receive a valid schema response

### GraphQL: bad request: field undefined
    
    Given I am a user
    
    And I query a nonexistent GraphQL type
    
    When I hit the GraphQL API
    
    Then I receive a field undefined error

### GraphQL: bad request: missing field
    
    Given I am a user
    
    And I query with a missing field
    
    When I hit the GraphQL API
    
    Then I receive a missing field error

## API Tests

### Login: Happy Path

    Given I am an existing user
    
    And I want to sign in
    
    When I hit the API

    Then I am signed in

### Login: email that contains leading and trailing whitespace gets trimmed
    
    Given I am an existing user
    
    And I want to sign in with an email that contains a leading and trailing space
    
    When I hit the API

    Then I am signed in

### Login: incorrect email
   
    Given I am an existing user
    
    And I want to sign in but my email is incorrect
    
    When I hit the API
    
    Then I am returned the error <CUSTOM ERROR>

### Login: incorrect password

    Given I am an existing user

    And I want to sign in but my password is incorrect
    
    When I hit the API

    Then I am returned the error <CUSTOM ERROR>
 
## Register User
 
### Register User - Happy Path
   
    Given I want to register as a user

    When I hit the API
    
    Then I have registered
    
    And I can sign in
    
### Register User: email address validation: subdomain email address (test@test.example.com)

    Given I want to create a user with a subdomain email address

    When I hit the API

    Then I have registered
    
    And I can sign in

### Register User: email address validation: second-level domain email address (test@example.co.uk)

    Given I want to create a user with a second-level domain email address

    When I hit the API
    
    Then I have registered
    
    And I can sign in

### Register User: email address validation: multiple periods the email address (test.test.test@example.com)

    Given I want to create a user with multiple periods in the email address

    When I hit the API

    Then I have registered
    
    And I can sign in

### Register User: email address validation: dash in domain of email address (test@qa-example.com)

    Given I want to create a user with a dash in the domain of the email address

    When I hit the API
    
    Then I have registered
    
    And I can sign in

### Register User: email address validation: plus sign in email address (test+qa@example.com)

    Given I want to create a user with a plus sign in the email address

    When I hit the API
    
    Then I have registered
    
    And I can sign in

### Register User: email address validation: long top-level domain in email address (test@example.museum)

    Given I want to register a user with a long top-level domain in the email address

    When I hit the API
    
    Then I have registered
    
    And I can sign in

### Register User: email address gets trimmed (" test@example.com ")

    Given I want to register a user with an email address that contains a leading and trailing space

    When I hit the API

    Then I have registered
    
    And the email address is trimmed
    
    And I can sign in
   
### Register User: email address syntax validation error (example123)
  
    Given I want to register a user with an invalid email address
    
    When I hit the API
    
    Then I am returned the error <CUSTOM ERROR>

### Register User: email address syntax validation error with special characters (qa+%%%()***///@example.com)
 
    Given I want to register a user with an invalid email address containing special characters
    
    When I hit the API
    
    Then I am returned the error <CUSTOM ERROR>

### Register User: email address strange invalid characters validation error (“(),:;<>[\]@example.com)

    Given I want to register a user with strange invalid characters email address

    When I hit the API

    Then I am returned the error <CUSTOM ERROR>

### Register User: emoji email address validation (test👾test@example.com)
    
    Given I want to register a user with an email address containing emoji
    
    When I hit the API
    
    Then I am returned the error ERR_VALIDATION_EMAIL

### Register User: emoji email address validation (test@example.co🫒)
    
    Given I want to register a user with an email address ending with an emoji
    
    When I hit the API
    
    Then I am returned the error <CUSTOM ERROR>

### Register User: space in email address validation (test test@example.com)
    
    Given I want to register a user with an email address containing a space
    
    When I hit the API
    
    Then I am returned the error <CUSTOM ERROR>

### Register User: double period before @ symbol (test..test@example.com)
    
    Given I want to register a user with an email address containing double period before @ sign
    
    When I hit the API
    
    Then I am returned the error <CUSTOM ERROR>

### Register User: double period after @ symbol (test@example..com)
    
    Given I want to register a user with an email address containing double period after @ sign
    
    When I hit the API
    
    Then I am returned the error <CUSTOM ERROR>

### Register User: double @ symbol (test@@example.com)
    
    Given I want to register a user with an email address containing double @ sign
    
    When I hit the API
    
    Then I am returned the error <CUSTOM ERROR>

### Register User: email address uniqueness validation

    Given I want to register a user with a pre-existing email address
    
    When I hit the API
    
    Then I am returned the error <CUSTOM ERROR>

### Register User: expected error when attempting to create user with same email address but with uppercase first character

    Given I am an existing user
    
    And I attempt to register again with an otherwise duplicate email address that has different case
    
    When I hit the API
    
    Then I have not created another user for myself
    
    And I am returned the error <CUSTOM ERROR>
    

### Register User: expected error when attempting to create user with same email address but all uppercase

    Given I am an existing user
    
    And I attempt to register again with an otherwise duplicate email address that is all uppercase
    
    When I hit the API
    
    Then I have not created another user for myself
    
    And I am returned the error <CUSTOM ERROR>
    
    
