# Spring Security OAuth 2.0 Guide

This example shows how to create a Authorization Server with Spring Security and OAuth 2.0.

Please read [A Quick Guide to OAuth 2.0 with Spring Security](https://developer.okta.com/blog/2019/03/12/oauth2-spring-security-guide) for a tutorial that shows you how to build the applications in this repo. 

**Prerequisites:** [Java 8 or 11](https://adoptopenjdk.net/).

> [Okta](https://developer.okta.com/) has Authentication and User Management APIs that reduce development time with instant-on, scalable user infrastructure. Okta's intuitive API and expert support make it easy for developers to authenticate, manage and secure users and roles in any application.

* [Getting Started](#getting-started)
* [Help](#help)
* [Links](#links)
* [License](#license)

## Getting Started

To install this example application, run the following commands:

```bash
git clone https://github.com/oktadeveloper/okta-spring-boot-authz-server-example.git
cd okta-spring-boot-authz-server-example
```

### Create an Okta Developer Account

Okta is a SaaS (software-as-service) authentication and authorization provider. We provide free accounts to developers so they can develop OIDC apps with no fuss. Head over to developer.okta.com and sign up for an account. After you’ve verified your email, log in and perform the following steps:

Go to Application > Add Application.
Select application type Web and click Next.
Give the app a name. I named mine “Spring Boot OAuth”.
Under Login redirect URIs change the value to http://localhost:8080/login/oauth2/code/okta. The rest of the default values will work.
Click Done.
Leave the page open of take note of the Client ID and Client Secret. 
You need to fill them into the file, as well as your Okta issuer URL. It’s gonna look something like this: dev-123456.okta.com. You can find it under API > Authorization Servers.

Update the `OktaOAuthClient/src/main/resources/application.yml` to have your new app's settings:

```yaml
okta:
  oauth2:
    issuer: https://{yourOktaDomain}/oauth2/default
    client-id: {yourClientId}
    client-secret: {yourClientSecret}
```

Start the `OktaOAuthClient` app using Gradle.

```shell
cd OktaOAuthClient
./gradlew bootRun
```

After everything starts, you should be able to log in with your credentials at `http://localhost:8080`.

## Links

This example uses the following open source projects:

* [Okta Spring Boot Starter](https://github.com/okta/okta-spring-boot)
* [Spring Boot](https://spring.io/projects/spring-boot)
* [Spring Security](https://spring.io/projects/spring-security)

## Help

Please post any questions as comments on this repo's [blog post](https://developer.okta.com/blog/2019/03/12/oauth2-spring-security-guide), or visit our [Okta Developer Forums](https://devforum.okta.com/). 

## License

Apache 2.0, see [LICENSE](LICENSE).
