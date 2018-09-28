# Under development

### Testing

For normal mocked testing run: `$tox`

For integration testing (testing against the real API):

1. Copy the `spt_keys_template.py` to a new file and call it `spt_keys.py` as this file will be automatically gitignored.
2. Now you can safely save your keys there for testing purposes. Here's an example:

    1. `SPOTIFY_CLIENT_ID` Create an app from [here](https://developer.spotify.com/dashboard/applications)
    2. `SPOTIFY_CLIENT_SECRET` Create an app from [here](https://developer.spotify.com/dashboard/applications)
    3. `SPOTIFY_ACCESS_TOKEN` Get a Spotify token from [here](https://beta.developer.spotify.com/console/get-current-user/)  ****Check all scopes**
    4. `SPOTIFY_ID` Get your Spotify ID from [here](https://www.spotify.com/account/overview/) 
    5. `PYFY_INTEGRATION_TEST` = true

3. Run `$tox`

*this will run some tests using your client ID, client secret, access token and user ID<br>
*Unfortunately Spotify does not have a sandbox API, so we have to test it against the live API<br>
*The tests will carefully teardown all resources created<br>
*Integration tests will not be abusive to the API and should only test for successfull integration with minimum API calls<br>