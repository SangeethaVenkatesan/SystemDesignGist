How the SSO works in general?

A secure authentication mechanism that allows other applications to get integrated into the system such that user
maintains one login for multiple apps under one ecosystem.

This is called Federated Identity - Sharing the identity across other service providers. 

Implementation:

1) SAML: Security Assertion Markup Language - An open XML based standard for exchanging identity between services. Its mostly
   used in work environment. If the app determines its a work domain, then it sends a SAML authentication request to the browser,
   The browser redirects the identity to the Identity Provider (Commerical Identity providers like Auth0). The Identity 
   provider then sends the SAML response back to the browser. This is called SAML Assertion. This XML document contains information
   about users, users accessibility. Now the browser sends the signed SAML assertion to the service provider. The service provider
   verifies (public key - private key cryptography). The service provider then sends the authorized resource back to the browser.
   
2) OpenID: This is what Google family uses. Similar to signed XML doc, openID passes JWT (Json) based document to the provider. 

Usage of both protocols depends on the application and use case. Both offers strong support towards different provider authetication 
schemes.

![Screenshot 2023-05-21 at 10 10 56 AM](https://github.com/SangeethaVenkatesan/SystemDesignGist/assets/68361331/fba6977b-bffa-48a6-ab8f-112614e102e5)
