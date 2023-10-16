# JAVA BUILD TOOLS

## Gradle 
    Initialize project: 
        gradle init 
        -> generated project structure: 
            .gradle: cache directory
            gradle: contains JAR files, CONFIGS OF GRADLE WRAPPER  
                wrapper
            gradlew: Mac, Linux for build (using Gradle Wrapper)
            gradlew.bat: Windows script for build (using Gradle Wrapper)
            settings.gradle.kts: settings files where the LIST of SUBPROJECTS is defined  
            app: contains 
                build.gradle.kts: build config  of java app 
                src: source code

    Build project:  
        gradlew build 
        -> build the project through gradlew (Gradle Wrapper) 
        -> all the build files go into the app/build folder (unless specify to another folder)

    General Gradle Project Structure: 
        settings.gradle.kts file 
            rootProject.name = "name"
            include("subfolder")

        Root Project folder
            libs.version.toml: VERSION CATALOG used for DEPENDENCY MANAGEMENT 
            Sub-Project1
                build.gradle.kts
            Sub-Project2
                build.gradle.kts
            ...
        * a build: 
            + Represents a BUNDLE of related software that you can: 
                + build
                + test 
                + release 
                -> together 

            + Can optionally INCLUDE OTHER BUILDS (vd: libraries, plugins, ...)

        * a project: 
            Represent a SINGLE PIECE of your ARCHITECTURE - a library, an app, plugin, ... 
            Can optionally CONTAINS OTHER PROJECT 

        * Setting file:     
            A project composed of 1 or more subprojects (modules)
            Gradle reads settings.gradle.kts file to figure out: which subprojects comprise(chua) a project build 

        * Build script:
            Each subproject contains its own build.gradle.kts file.

            build.gradle.kts: defines tasks to build project 

            -> Task: a BASIC UNIT OF WORK that can be done by Gradle as part of the build (call gradlew tasks to see all the tasks can be done in the project)
                vd: gradlew build 

                -> Create your own tasks (from built-in tasks)
                    popular built-in tasks:
                        + Copy
                        + Delete 
                        + Exec: execute O/S command 
                        + Zip: bundle files
                -> Dependencies between tasks (vd: task b input is task a output)
                    -> statement dependsOn("task")

            -> Dependencies management: 
                Project dependencies:  
                    IN GRADLE.BUILD.KTS FILE:
                        2 section: 
                            + repositories: 
                                -> the SOURCE of dependencies (vd: mavenCentral)
                            + dependencies: 
                                -> dependencies declarations via config types (vd: testImplementation, implementation)
                                -> need SPECIFIC INFO to find a depedency 
                                    -> format: "Group:Name:Version"
                                    vd: com.google.guava:guava:32.1.2-jre

                Transitive Dependencies: dependencies of a dependency 
                    vd: for guava dependency to work, it needs failureaccess dependency

                -> Can VIEW DEPENDENCY TREE using command: gradlew :app:dependencies
                -> Can BUILD SCAN the project and SHARE THE RECORD WITH TEAM 

            -> Update Dependencies: by changing the version in the build file 

            -> Version catalog (libs.versions.toml):  
                -> declare all DIRECT dependencies of a project in a CENTRAL LOCATION 

            -> Plugins: 
                is the primary method for: 
                    + organize 
                    + reuse 
                    build logic 
                    + distribute custom tasks as packaged code

                -> EXTEND Gradle's core FEATURES 
                plugin can:
                    + ADD tasks to the project (eg: compile, test)
                    + EXTEND the basic Gradle model (e.g: add new DSL elements that can be configured)
                    + ....

                **Still not really understand why i should use it ??  

    Questions: 
        Gradle wrapper ?? 
            the things that helps starting Gradle build (even if you DON'T HAVE GRADLE INSTALLED)
            -> it reads the gradlew file to CHECK THE GRADLE VERSION TO USE (if needed download that version)
            -> KEEP THE SAME GRADLE VERSIONS FOR DIFFERENT MACHINES  
            -> NEVER INVOKE GRADLE DIRECTLY, USE IT THROUGH GRADLE WRAPPER 

        What is build script DSL ?? 
            -> Domain Specific Language 

        What is a build scan ?? 
            is a record of a build (that can be shared, and centralized)
            -> have shareable record (share with team) about your build 
                including insights into:
                    + performance
                    + dependencies 
                    + test results