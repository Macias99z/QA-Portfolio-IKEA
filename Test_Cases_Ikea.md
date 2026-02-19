# Test Cases - Search Functionality

## TC-01 Search with valid product name

Type: Functional

Preconditions:

- User is on IKEA homepage

Steps: 

1. Enter "sofa" in search field
2. Click search

Expected result: 

- List of products related to "sofa" is displayed

Status: PASS

## TC-02 Search with non-existing product

Type: Functional

Steps:

1. Enter "qwertyuiop12345" in search field
2. Click search

Expected Result: 

- Message indicating no results found is displayed

Status: PASS

## TC-03 Search with an empty input

Type: Boundary Testing

Steps:

1. No information entered in the search window
2. Click search

Expected result: The page does not respond to user queries, nothing happens when the Enter/Search key/button is pressed.

Status: PASS 


## TC-04 User searches using very long input(500 character)

Type: Boundary testing

Steps:

1. User enters 500 characters query
2. Click search

Expected result: The search field will have a character limit of 100-200. 

Actual result: The front-end doesn't block data entry. The backend processed the query and returned a valid message indicating no results.

Conclusion: Lack of validation on the UI side may lead to buffer overflow or DoS attacks if processing takes too long.

Status: FAIL

## TC-04 User searches using special characters

Type: Edge Testing

Steps: 

1. Enter "#$%^%#@" in search field
2. Click search

Expected result: Message indicating no results found is displayed, no other errors.

Status: PASS

## TC-05 User searches using emojis

Type: Edge Testing

Steps:

1. Enter "😊🙂" in the search field
2. Click search

Expected result: The system will return no results or ignore the character

Actual result: The system returned a list of products emotionally associated with the symbol (stuffed animals, toys).

Conclusion: The IKEA search engine uses advanced Natural Language Processing algorithms or keyword matching to emojis. The system is resistant to unusual characters and attempts to "understand" the user's intention instead of returning an error. 

Status: PASS

## TC-07 User searching using uppercase letters

Type: Edge testing

Steps: 

1. User enters "SOFA" in the search field
2. click search

Expected result: System will treat is as normal query just as it was written in the lowercase letters. 

Status: PASS