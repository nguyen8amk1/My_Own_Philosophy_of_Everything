# ACORN 
## What is Acorn ? 
A PLATFORM that make things easy:
    + build 
    + share
    + run containerize apps.     

Provide: 
    comprehensive way to DESCRIBE your APPLICATIONS and DEPENDENCIES in a SINGLE FILE called Acornfile
    -> BUILT and PACKAGED up into a SINGLE ARTIFACT that contains everything needed to deploy your application. 
    -> can be SHARED WITH A LINK 
    that will ALLOW IT'S RECIPIENTS 
    to have A ONE-CLICK DEPLOYMENT 
    -> 1 click deployment into sandbox environment 

## Key features: 
## Sandbox: 
    FREE compute ENVIRONMENT in the cloud 
    2 hours at a time 
    Acorn launched in the sandbox environment can be 
    ACCESSED via PUBLIC URL with SSL. 
    INTERACTED through CLI or UI 

## Acornfiles and Acorn Images: 
    Acornfile: 
        simple way to DESCRIBE: HOW TO DEPLOY:
                                    + containers
                                    + services 
                                    + volumes 
                                    + secrets
                                    + jobs 
                                    + configurations 

        Supports AUTO UPGRADING when new Acorn images are published to a registry 

## Sharable Acorn links: 
    The one who click can deploy the app into their own Acorn Sandbox 


Acorn also have it's own build file called Acornfile 
just like Docker with Dockerfile 
vd: 
containers { 
    web: { 
        build: "."
        ports: publish: "5000/http"
    }
}
