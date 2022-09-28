# JWT

JWT are cryptographically signed tokens that can be decoded by anyone, and can also be verified with a public key. 
This way we can know who created them. 
They are issued to a client and can be used by the client to verify that they have certain claims.
For example, the claim of identity, or role.

One claim is exp, which tells when the token should expire.

They are made of three sections: the Header, Payload, and Signiture.

The Header gives the alorithm used.

The Payload contains the claims that can be verified with the Signiture.

## What is secure about JWT?

The JWT can be decoded easily by anyone. For example at this website: https://jwt.io/#debugger-io

But it can't be forged or changed. That makes the claims provable. This is done using the signiture. 
If the claims were to be changed, the signiture would no longer match with the payload. This can be checked.

