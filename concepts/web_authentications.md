# HOW WEB AUTHENTICATION WORKS 
The COMMUNICATION between clients and servers over HTTP: STATELESS 
    -> server CAN NOT CONFIRM the IDENTITY of client (without some sort of authentication)

Store password hash on the database (instead of plaintext)
    -> a SALT value would probably added to the password before hashing 
        (to prevent the Rainbow table attack)
    SALT is unique for each password
    PEPPER is the same as SALT but get REUSE for all the password in the system 

The server HANDLES each request INDEPENTLY: 
    -> server doesn't remember what you did some time ago on the website ? 
    -> But the client does :v 
    -> the CLIENT tells in each request WHO THEY ARE and WHAT RESOURCEs they NEEDED (store in cookie)
    -> the cookie get send to the Server to verify (in every request)
    -> The data store in Cookie(Client side) called: RememberToken 
    -> RememberToken is generated from Server and also get stored in the Database (as another field in the User table)

## JWT (JSON Web Token)
    digitally signed using a private key 
    -> the token can be verified by other parties with public key 
    -> The purpose is NOT TO HIDE data, but to ensure the AUTHENTICITY of the data
    -> Server DON'T need to STORE RememberToken on Database

    Structure: 
        header.payload.signature

        header: 
            + token type 
            + algorithm use for signing and encoding

        payload: session data
            + Issuer
            + Subject 
            + Audience
            + Expiration date
            + Issued at 
            -> Do not put sensitive informations 

        signature: 
            + encoded from header and payload (use private key from Identity Provider)

    How it works(Authentication): 
        1. Identity Provider (Authentication Server) generates a JWT 
            -> verify the credentials (username, password, ...) -> return JWT 

        2. Resource Server: Verifies JWT 
            -> verify the JWT -> return resources  

        JWT payload can contains many user info that can be used for Authorization (such as role,...)

        Access Token: 
            use to:
                + authorize requests 
                + store additional information about the user (payload) (id, roles, ...) as part of the business logic 

            -> Should store in the memory of the application -> not LocalStorage or other place that can be easily hacked 

        Refresh Token: 
            use to obtain new pair of access or refresh tokens without a complete login 
            -> stored on the server/database as well -> account for access and invalidate stolen tokens 

            -> Store in an httpOnly Cookie 
            -> Only the server can read the cookie, not through JS (on the client side)
            -> Longer lived than access token 


    Authorization: 
        determining what ACTIONS or RESOURCES a user is ALLOWED TO ACCESS or PERFORM after they've been authenticated.

        5 Implementations (Access Control): 
            1. Role-based: 
                this is a common approach 
                -> USERS are assigned ROLES 
                -> ROLES are assigned specific PERMISSION 
                -> Users inherit the permissions associated with their assigned role 
                vd: 
                    Admin Role: can access and modify data
                    Editor Role: can edit content but not access user management. 
                    Viewer Role: can only view content.

            2. Attribute-based: 
                more fine-grained approach: 
                -> consider BOTH: 
                    + user attributes
                    + resources attributes
                    to make access control decisions

            3. Access-control list: 
            4. Permission Hierarchies: 
            5. Policy-based Authorization: 

        -> To implement:
            INTERGRATE the authorization step INTO THE APPLICATION CODE 
            performed when: 
                user attempt to ACCESS A RESOURCE 
                PERFORM AN ACTION
                -> if pass the authorization check -> granted access
                -> else -> denied  
            -> Implementing ERROR HANDLING FOR UNAUTHORIZED ACCESS is crutial for security 
    pros: 
    cons: 
        Must use https to secure the JWT 
        Can't completely rely on the algorithm mentioned in the header of JWT.
        REVOKING(thu hoi) the session of a user is DIFFICULT

SESSION VS JWT: 
    session:
        required data is on the physical database 
        -> it's a like a ticket 
    jwt: 
        contain actual information for the server to use 
        -> it's like a document 
        -> can scale very well, since no data depedencies for the server 
        


Middleware function: 
    a hook that INTERCEPT BETWEEN request and response 
    can: 
        + Make changes to the request and response objects 
        + End the request-response cycle 
        + CALL the NEXT MIDDLEWARE in the stack
    types: 
        Application level: app.use
            vd: Auth middleware 
        Router level: router.use
