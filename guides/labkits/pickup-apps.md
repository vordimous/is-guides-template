# Pickup Apps

1. Once IS is [running](../README.md#run-identity-server), login to the console app [localhost:9443/console](https://localhost:9443/console) using `admin:admin` user:pass

1. Create two `New Application` using the `Web Application` template

    - __Name__ `Pickup-Dispatch` app with __Redirect URL__

      ```text
      http://localhost.com:8080/pickup-dispatch/oauth2client
      ```

    - __Name__ `Pickup-Manager` app with __Redirect URL__

      ```text
      http://localhost.com:8080/pickup-manager/oauth2client
      ```

1. Update __Self Registration__ by selecting the `Manage` tab -> `User Onboarding` section

    - set `User self registration` to *Enabled*
    - set `Prompt reCaptcha` to *Disabled*
    - submit changes

1. Follow the [Run Web Apps](../../README.md#pickup-apps) instructions to update the tomcat apps with the correct configuration and `clientKey` & `clientSecret`.

1. *Important*: The next steps must be in `Firefox`

1. In a new browser session navigate to the [Pickup-Dispatch app](http://localhost.com:8080/pickup-dispatch) and click the `Login` button

1. Register a new user

1. Open the [local mailserver](http://localhost:8025/)

1. Activate the new user by clicking the activation like in the registration email.

1. If you are not redirected, navigate back to the [Pickup-Dispatch app](http://localhost.com:8080/pickup-dispatch) and `Login` with the newly created user

1. Navigate to to the [Pickup-Manager app](http://localhost.com:8080/pickup-manager/oauth2client) and `Login`. The new user is already logged in.

1. In the user menu on click the `Logout` option

1. Navigate back to the [Pickup-Dispatch app](http://localhost.com:8080/pickup-dispatch) and the user is already logged out
