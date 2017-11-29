# Sessions

- Sessions are used so that the app has some understanding of _who_ is sending the requests
- Default is that is stored in the cookie
- The cookie is sent back and forth with each request/response
- You need to be careful if the cookie has any information that shouldn't be public, and also make sure its not too big (otherwise, slow)

## Security implications
- Storing sessions in the cookie (Rails default) can open you up to a Replay Attack
- This is when the user takes information stored in the cookie to send incorrect data back to the server
- Including a nonce (random value) can solve replay attacks, but the server has to keep track of them and it gets complex if you are running multiple servers
- Storing it in the database means you can invalidate a session without nuking all cookies
