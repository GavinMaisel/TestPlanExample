# Examples of Automated Tests written in Gherkin (Given/When/Then) format
## These tests can act as a Product Catalog of existing business functionality


# Login UI Tests

## Login_Success
    
    Given I am an existing user who is logged out
    
    When I log in
    
    Then I am logged in

## Login_Success_for_Mobile_View
    
    Given I am an existing user on mobile view
    
    When I log in on mobile view
    
    Then I am logged in on mobile view

## Unable_to_Login_with_Non-Existent_Email
    
    Given I am a guest on the login page
    
    When I try to log in with a non-existent email address
    
    Then I see the error invalid username/password

## Unable_to_Login_with_Incorrect_Password
    
    Given I am a guest on the login page
    
    When I try to log in with an incorrect password
    
    Then I see the error invalid username/password

## Unable_to_Login_with_Invalid_Email_Address_Format
    
    Given I am a guest on the login page
    
    When I enter an invalid email
    
    Then I see an error for invalid email
    
    
# GraphQL Schema Tests

## GraphQL: schema

  Given I am a user
  
  And I want to query the schema
  
  When I hit the GraphQL API
  
  Then I receive a valid schema response

## GraphQL: bad request: field undefined
    
    Given I am a user
    
    And I query a nonexistent GraphQL type
    
    When I hit the GraphQL API
    
    Then I receive a field undefined error

## GraphQL: bad request: missing field
    
    Given I am a user
    
    And I query with a missing field
    
    When I hit the GraphQL API
    
    Then I receive a missing field error

# API Login

## Login: Happy Path

    Given I am an existing user
    
    And I want to sign in
    
    When I hit the API

    Then I am signed in

## Login: email that contains leading and trailing whitespace gets trimmed
    
    Given I am an existing user
    
    And I want to sign in with an email that contains a leading and trailing space
    
    When I hit the API

    Then I am signed in

## Login: incorrect email
   
    Given I am an existing user
    
    And I want to sign in but my email is incorrect
    
    When I hit the API
    
    Then I am returned the error <CUSTOM ERROR>

## Login: incorrect password

    Given I am an existing user

    And I want to sign in but my password is incorrect
    
    When I hit the API

    Then I am returned the error <CUSTOM ERROR>
    
   
