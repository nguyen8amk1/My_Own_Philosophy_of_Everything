# Docker 

+ What TYPE of TOOL is this ?
    ... 

+ What the REASON it created ? 
    a wrapper that wrap a piece of software along with everything it needed to run 
        vd: code, runtime, system tools, system libraries - anything that can be installed on a server 
        -> software will always run the same 
    -> the kind of problems they best suited: Wrapping the software along with their running environment to run on other platform 

+ How to USE it ? 
    3 important concepts: 
        Container:
            A running instance of an image 
            Sandbox process running on host machine that isolated from all other processes 
                -> have it's own software, binaries, configurations, ... -> contained in Image 

        Image: 
            -> A blueprint for a containers (a class - object relationship)
            contains everything needed to run an application 
                -> 
                dependencies,
                configurations,
                scripts,
                binaries,
                environment variables,
                metadata,
                default command to run, ...

            Made up of different layers
                1. Parent image: 
                    Includes the OS & run-time environment 
                The rest of the layers is about modifying the parent image to suit our needs 
                    2. source code
                    3. dependencies
                    4. ...
                vd:
                    FROM node:17-alpine #parent image -> 1st layer

                    WORKDIR /app # set the working directory 

                    COPY . . # copy the source code in the current folder to the working dir 

                    RUN npm install # install the dependencies AT BUILD TIME 
                        -> RUN command at build time 

                    EXPOSE 4000 (Set which ports the container should expose to the machine)

                    CMD ["node", "app.js"] # command to run at RUN TIME


        Dockerfile: 
            contains script of instructions 
            -> all the COMMANDS a user could CALL ON THE COMMAND LINE to assemble an image.  
            + format: 
                INTRUCTION arguments 
            Docker file instructions run in order 

            Start with: 
                FROM <parent image>


    Share Docker images: 
        -> images is shared through Docker registry 
        vd: Docker Hub (kinda github but for images) - the default 

    Flow: Dockerfile --(build)-> Image --(run)-> Container 

    Mount: 
        Volume mount: 
            Persist Data between containers:
                Each containers is isolated -> no file sharing between them 
                -> Volumes is a feature that stick a sharing data between the containers 
                -> VOLUME MOUNT -> Persist the Data in Database 
                    -> when need somewhere persistent to store application data 

        Bind Mount: 
            Share directory:
                + from the host's file system 
                + to the container 
                -> can use it to mount source code into the container
                    -> have a container that watches the filesystem changes and respond to them.

            -> IMPORTANT: Can use for local development setup which contains all the dependencies and runtime environment 

    Multi-containers app:         
        + 

    Systemmaticaly control multi-containers: 
        -> using Docker compose 
        -> Instead of initilizing containers using docker run command 
        -> We have a compose file to actually specify all of the works need to be done 

    -> IMPORTANT: 
        Use docker compose volumes feature to create a local development environment  


+ What makes it UNIQUE ? 
    ...
    -> understanding the: 
        + capabilities 
        + constraints 
        -> help you pick the right tool for the job 

What is a DOCKER CONTAINER: 
    a wrapper that wrap a piece of software along with everything it needed to run 
        vd: code, runtime, system tools, system libraries - anything that can be installed on a server 
        -> software will always run the same 

What is DOCKER COMPOSE: 
    Compose is a tool for defining and RUNNING MULTI-CONTAINER Docker applications
    ....