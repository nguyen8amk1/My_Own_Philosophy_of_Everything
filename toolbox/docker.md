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
            contains everything needed to run an application 
                -> 
                dependencies,
                configurations,
                scripts,
                binaries,
                environment variables,
                metadata,
                default command to run, ...

        Dockerfile: 
            contains script of instructions 
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