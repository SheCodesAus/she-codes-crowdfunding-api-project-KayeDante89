# Link to Document with API Spec, Data Schema and link to Deployed site:

https://drive.google.com/file/d/1hnsjTdGnZ5vR1NIf7bGd_asemN3_GVxQ/view?usp=sharing

# Project Title: Love Ledger
​
This is a crowdfunding app for engaged couples to create a fundraising campaign to collect money from their friends and family to help pay for their wedding expenses. This app would typically include features such as the ability to create a campaign page and accept donations in the form of payments and track its progress in reaching their target goals. This app would be used by engaged couples (or any persons wanting to raise funds for another person’s wedding etc) to fund expenses such as venue rental, catering, photography and their honeymoon as well.
​
## Features
​
### User Accounts
​
- [X] Username
- [X] Email Address
- [X] Password
​
### Project
​
- [X] Create a project
  - [X] Title
  - [X] Owner (a user)
  - [X] Description
  - [X] Image
  - [X] Target Amount to Fundraise
  - [X] Open/Close (Accepting new supporters)
  - [X] When was the project created

- [X] Ability to pledge to a project
  - [X] An amount
  - [X] The project the pledge is for
  - [X] The supporter
  - [X] Whether the pledge is anonymous
  - [X] A comment to go with the pledge
  
### Implement suitable update delete
​
**Note: Not all of these may be required for your project, if you have not included one of these please justify why.**
​
- Project
  - [X] Create
  - [X] Retrieve
  - [X] Update
  - [X] Destroy
- Pledge
  - [X] Create
  - [X] Retrieve
  - [X] Update
  - [X] Destroy
- User
  - [X] Create
  - [X] Retrieve
  - [ ] Update -- I didn't bother with this feature
  - [ ] Destroy -- I didn't bother with this feature
​
### Implement suitable permissions
​
**Note: Not all of these may be required for your project, if you have not included one of these please justify why.**
​
- Project
  - [X] Limit who can create
  - [ ] Limit who can retrieve -- Not necessary
  - [X] Limit who can update
  - [X] Limit who can delete
- Pledge
  - [X] Limit who can create
  - [ ] Limit who can retrieve -- Not necessary
  - [X] Limit who can update
  - [X] Limit who can delete
- User
  - [ ] Limit who can retrieve -- Not necessary
  - [X] Limit who can update
  - [X] Limit who can delete
​
### Implement relevant status codes
​
- [x] Get returns 200
- [x] Create returns 201
- [x] Not found returns 404
​
### Handle failed requests gracefully 
​
- [X] 404 response returns JSON rather than text
​
### Use token authentication
​
- [X] implement /api-token-auth/
​
## Additional features
​
- [X] Change Password
​
Allows users to change old password to a new one.
​
- [X] Filtering
​
You can filter through Projects/Pledges to view by owner/supporter or whether the Project is open or not.
​
- [X] Search Filter
​
Can search key words in Title and Description
​
### External libraries used
​
- [X] django-filter
​
​
## Part A Submission (please see DocLink on the top of page.)
​
- [X] A link to the deployed project.
- [x] A screenshot of Insomnia, demonstrating a successful GET method for any endpoint.
- [x] A screenshot of Insomnia, demonstrating a successful POST method for any endpoint.
- [x] A screenshot of Insomnia, demonstrating a token being returned.
- [x] Your refined API specification and Database Schema.
​
### Step by step instructions for how to register a new user and create a new project (i.e. endpoints and body data).
​
1. Create User

```shell
curl --request POST \
  --url http://localhost:8000/users/ \
  --header 'Authorization: Bearer ' \
  --header 'Content-Type: application/json' \
  --data '{
	"username": "kflam4",
	"email": "k4@flam.com",
	"password": "password"
}'
```

2. Sign in User
​
```shell
curl --request POST \
  --url http://localhost:8000/api-token-auth/ \
  --header 'Authorization: Bearer undefined' \
  --header 'Content-Type: application/json' \
  --data '{
	"username": "admin",
  	"password": "password"
}'
```
​
3. Create Project
​
```shell
curl --request POST \
  --url http://localhost:8000/projects/ \
  --header 'Authorization: Token d1a64d3eeea1d0075e33afd074a3b3e2905197e1' \
  --header 'Content-Type: application/json' \
  --data '{
	"title": "Funds for Photography",
	"description": "Help us fund our photographer!",
	"goal": 1500,
	"image": "https://th.bing.com/th/id/R.6c1536e2841d8ad3e8281abaa8a8e38e?rik=ZZ6K7Ny0VVexlg&riu=http%3a%2f%2fsaltlakebride.com%2fwp-content%2fuploads%2f2017%2f11%2fWedding_Venue_1.jpg&ehk=UfSL9AJuNl1K7Ex6Tk6rHm8sRdgMDx0xSCLn2vwpoNA%3d&risl=&pid=ImgRaw&r=0",
	"is_open": "True",
	"date_created": "2023-01-29T04:13:24.473Z"
}'
```
