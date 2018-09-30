# REST Authentication Methods


## Static - Key

The term **key** is used to denote a static value that is passed to a REST endpoint. Only one GET request is needed to authenticate and access the REST endpoint.


### Authentication Retrieval/Submission Methods


#### URL


##### Type

GET


##### URL

`www.example.com?id=123&key=abc`


##### Header

None


#### Bearer Header


##### URL

`www.example.com?id=123`


##### Header


###### Key

Authorization


###### Value

Bearer abc


#### Custom Header


##### Type

GET


##### URL

`www.example.com?id=123`


##### Header


###### Key

APIKEY


###### Value

abc


## Dynamic - Token

The term **token** is used to denote a dynamic value that is requested in a POST request which returns a token that is then used in a GET request. The POST request is required to retrieve the authentication token, followed by a GET request to access the REST endpoint.


### Authentication Retrieval Methods


#### Username/Password


##### Type

POST


##### URL

`auth.example.com`


##### Body

username=user1&password=pass1


##### Header

None


##### Output

{'APITOKEN', 'abc'}


#### Custom Header


##### Type

POST


##### URL

`auth.example.com`


##### Body

None


##### Header


###### Key

KEY


###### Value

abc


##### Output

{'APITOKEN', '123'}


### Authentication Submission Methods


#### Bearer Header


##### URL

`www.example.com?id=123`


##### Body

None


##### Header


###### Key

Authorization


###### Value

Bearer abc


##### Output

{'id', '123', 'widget', 'abc'}


#### Custom Header


##### URL

`www.example.com?id=123`


##### Body

None


##### Header


###### Key

APITOKEN


###### Value

abc


##### Output

{'id', '123', 'widget', 'abc'}
