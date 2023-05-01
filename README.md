# OAuth2

## Authorization Flows

### Authorization Code Flow

![](assets/authorization-code-flow.png)

- Client does not have access to `resource owner`'s credentials
- Authorization server needs the resource owner's credentials to trust her/him, that's why client redirects resource owner to authorization server to input the credentials.
- Token does not returns back in redirects, token is issued by using client's request in back channel.
- ClientId and ClientSecret are sent using authorization headers in base64 format.
- For more info, see [Access Token Request / RFC 6479](https://datatracker.ietf.org/doc/html/rfc6749#section-4.1.3)

### Authorization Implicit Flow

> This flow is deprecated

![](./assets/authorization-implicit-flow.png)

- This flow is desined for client's with type public (non-confidential) like JavaScript or native applications.
- Client does not have access to `resource owner`'s credentials

### Resource Owner Password Credentials Flow (ROPC)

> This flow is deprecated

![](./assets/resource-owner-password-credentials-flow.png)

- This flow is designed for trusted clients! for example, facebook app is a trusted client for facebook itself! 
- Client **has access** to `resource owner`'s credentials

### Client Credentials Flow

![](./assets/client-credentials-flow.png)

- In client credentials flow, the user does not have any role!
- Client should be a confidential client, otherwise, it will have security issues

## Federation Gateway

![](./assets/federation-gateway.png)

![](./assets/federation-gateway-with-internal-idp-block-diagram.png)

![](./assets/federation-gateway-with-internal-idp-sequence-diagram.png)

## Notes
- Audience of the access token is not the client, but the server owner
- Audience of the id token is the client
- Relying party is the application who relies on IDP, it does not have any authentication/authorization but relies on IDP