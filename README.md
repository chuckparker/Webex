# Webex
Remember Me
The default is for the remember me option to be set to false.  by changing the value to true and posting to your Control Hub you can enable this remember feature and for SSO user of Webex Teams the company will no longer receive multiple prompts at login.
Contributors; Brett Wiggins, Collaboration TSA and Nick Wooler, Product Manager

Once authenticated as admin on webex.com
developers tool menu
click on users tab in clontrol hub
select user
find bearer token for authorization
copy everything including bearer
Postman
	Header
		Authorization  - paste bearer token in as bearer
Send as a GET     https://idbroker.webex.com/idb/idbconfig/"account-id"/v1/authentication

a response should be returned
{
	"EmailAsUid": true,
	"JITCreation": false,
	"JITUpdate": false,
	:LKeepMeSignedIn": true,
	"KeepMe SignedInDuration": 14,
	"RememberMyLoginId": false,
	"RememberMyLoginIdDuration": 30,
	"schemas": [
		"urm:cisco:codec:identity:idbroker:authenconfig:schemas:1.0"
	]
}

Change RememberMyLoginId from false to true

Change from a GET to PATCH
Change from Body to Raw format and then paste the modified script into the body window of postman
Send the PATCH 
expect an accept back
Test by opening your Webex home page and verify the remember me button is present
  




