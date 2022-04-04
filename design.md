## Design of the LOTR SDK

The SDK is contained within a single class which is initialized with the API token of the user.

Each method uses the get_resource function to build a request using the base url of the one API and the user provided api token. 

Requests are submitted to the one API, and the json responses are parsed into python dictionaries and returned to the user.