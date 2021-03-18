# Snapvocab
SnapVocab helps language students learning words that are most useful to them

## URL
https://snapvocab.com

## Application Architecture - Serverless Stack - Production Environment
![application_architecture](/misc/application_architecture_serverless.png)

Infrastructure as Code Tool : AWS CDK + AWS Serverless Application Model

Note: containers stack architecture - learning purposes only - is available [here](https://github.com/Jayrome974/learnusefulwords).

## Modules
* Static WebContent: Vue.js 3, JavaScript, Mobile Responsive, OAuthClient
* Backend: Lambda, REST API, DynamoDB, Java 11
* Mobile APP: iOS, Swift 5, Cocoapods, UIkit, Storyboard, OAuthClient

## Screenshots
* Website
![snapvocab_webiste_screenshot](/misc/snapvocab_website.png)

* iOS APP

![snapvocab_ios_screenshot](/misc/snapvocab_ios.png)

## Lambda backend functions
### Use Cases
#### Add a word in the library
* Input : a word
* Output : N/A
* Primary Course : 
1. Validate the word
2. Find that word in the library
3. If not found, create Word in the library
4. Else, increment number of occurrences of that word by 1 in the library

#### List 10 useful words from the library
* Input : N/A
* Output : List of words
* Primary Course :
1. Find 10 words that appear at least 3 times in the library

#### Delete a word in the library
* Input : a word ID
* Output : N/A
* Primary Course : 
1. Delete the word with the given ID in the library

#### Add an email in the mailing list
* Input : an email
* Output : N/A
* Primary Course : 
1. Validate the email
2. Create Email in the mailing list

### REST API Design
#### Resource : addingsword
##### Perform an adding of word


`POST /addingsword`


INPUT
* word | string | required

RESPONSE
* Status : 200 OK

#### Resource : Words

##### List 10 words that appear at least 3 times in the library


`GET /words`


INPUT
* N/A

RESPONSE
* [ { id | string, word | string, nbOccurrences | int}, ... ]
* Status : 200 OK

##### Delete a word

`DELETE /words/:wordId`

INPUT
* N/A

RESPONSE
* Status : 204 No Content

#### Resource : addingsemail
##### Perform an adding of email


`POST /addingsemail`


INPUT
* email | string | required

RESPONSE
* Status : 200 OK
