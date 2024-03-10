Navigation | [[Table Of Contents]](README.md#navigating-the-documentation)


# Key Terminology

* **Application**: A computer program that performs specific functions, and may interact with other applications or with users over a network. The terms 'application' and 'service' are used interchangeably in this document.

* **Operators**: Applications that automate human operator actions, such as a MySQL operator managing a MySQL database lifecycle.

* **Jobs**: Applications invoked by a pre-defined schedule or events.

* **Resource Owner/User**: The end user who authenticates and provides consent for a client application to access their resources.

* **Relying Party/Client**: The client application that uses OAuth 2.0, relies on the OpenID provider for user authentication, and requests user claims. Client obtains authorization from the resource owner, and is identified via authorized party (azp) claim in OIDC.

* **Scope**: Identifiers for resources that a client wants to access. These identifiers are sent to the OIDC Provider during an authentication or token request.

* **Authorization Server/OIDC Provider (OP)**: The server that the user interacts with when an application requests access to their account/resources. It provides the access token required by the client to access the protected resources.

* **Authorized Party**: Contains the relying-party identity in the `azp` claim of the OIDC spec. It adds authenticity to the end-user access token presented by the relying-party to the resource server.

* **Authorized Forwarder**: Introduced by TrustFabric, the `azf` claim allows resource servers to present the resource owner's access token to upstream dependencies. It is particularly useful in the microservices world where monolith applications are refactored and finer grained authorization needs to follow suit.

* **Resource Server**: An API server that allows access to the user's information or resources. It can accept and respond to protected resource requests using access tokens, and may also act as relying party in a multi-step transaction where it obtains the delegation grants based on authorized forwarder (azf) claim.

* **Application Fabric Layer**: A virtual representation of a trust established between applications for interactions based on their identities and audience claims (`aud`).

* **Session Layer**: Represents sessions established by the resource-owner with the applications. It requires the application fabric as a building block for trusting applications.

* **Authorization Code**: Represents the resource-owner's authenticated consent to authorize the relying party. TrustFabric distinguishes between the code grant for generation of application identities (Bootstrap code, used in Application Fabric Layer) and resource-owner initiated code-grant (Authorization Code, used in Session Layer).

* **Access Token**: A bearer token presented by the application or relying-party to gain access to the resource-server. There are two types:
  * _Application Access Token:_ Represents the application identity, where the `sub` claim refers to application identity and `aud` claim represents target applications this subject interacts with.
  * _User Access Token:_ An access token given to relying party by the user. The `sub` claim represents the resource owner, while `azp` claim represents the relying-party or client identity. Similarly `azf` claim represents the applications that can present the access token on behalf of the user.

* **Refresh Token**: A token used by the client or application to refresh the access token. Just like access token, there are two kinds:
  * _Application Refresh Token:_ Refresh token for application identity
  * _User Refresh token:_ Refresh token for user access token