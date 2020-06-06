# Utility
GET /applications/grants
Status: 200 OK
Link: <https://api.github.com/resource?page=2>; rel="next",
      <https://api.github.com/resource?page=5>; rel="last"
[
  {
    "id": 1,
    "url": "https://api.github.com/applications/grants/1",
    "app": {
      "url": "http://my-github-app.com",
      "name": "my github app",
      "client_id": "abcde12345fghij67890"
    },
    "created_at": "2011-09-06T17:26:27Z",
    "updated_at": "2011-09-06T20:39:23Z",
    "scopes": [
      "public_repo"
    ]
  }
]
GET /applications/grants/:grant_id
Status: 200 OK
{
  "id": 1,
  "url": "https://api.github.com/applications/grants/1",
  "app": {
    "url": "http://my-github-app.com",
    "name": "my github app",
    "client_id": "abcde12345fghij67890"
  },
  "created_at": "2011-09-06T17:26:27Z",
  "updated_at": "2011-09-06T20:39:23Z",
  "scopes": [
    "public_repo"
  ]
}



curl -u username:token https://api.github.com/user
curl -v -H "Authorization: token TOKEN" https://api.github.com/repos/octodocs-test/test
X-GitHub-SSO: required; url=https://github.com/orgs/octodocs-test/sso?authorization_request=AZSCKtL4U8yX1H3sCQIVnVgmjmon5fWxks5YrqhJgah0b2tlbl9pZM4EuMz4
{
  "message": "Resource protected by organization SAML enforcement. You must grant your personal token access to this organization.",
  "documentation_url": "https://help.github.com"
}
curl -v -H "Authorization: token TOKEN" https://api.github.com/user/issues
X-GitHub-SSO: partial-results; organizations=21955855,20582480
curl --request POST \
  --url https://api.github.com/authorizations \
  --header 'authorization: Basic PASSWORD' \
  --header 'content-type: application/json' \
  --header 'x-github-otp: OTP' \
  --data '{"scopes": ["public_repo"], "note": "test"}'
  
