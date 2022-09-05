Pages listed below,
1. `/` (Login) - Root of our page is login screen. If user already logged in and the token is in valid then they will be redirected to respective home screen according to their role.

2. `/check-mobile` (OTP verifier) - Those who are trying to login/signup through mobile number, they will be redirected to this page.

3. `/check-email` (page for Email link placeholder) - Those who are trying to login/signup through email, they will be redirected to this page. Infographics shown so that user will know the email sent to their email.

4. `/verify-magic-link` (Email verifier) - Page where email will be validated and will redirect user to appropriate pages from here after verification. Loader shown while processing.

5. `/profile_setup` (New user profile setup) - User can select thier role, name from this page. 

6. `/verify` (email related verifier) - Like google, microsoft authendicator page.  Loader shown while processing.

7. `/unauthorised` - If user is not authorised, for pages they are trying to access. They will redirect to this page.

8. `*` - Not found page if the url is not available.


Other pages are based on user roles: `/admin`, `/teacher`, `/student`. On signup, every user will be redirected to `welcome` pages according thier role. From welcome page, user can navigate to home screen. from second time, user will be redirected to home screen.
