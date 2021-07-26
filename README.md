# codecoach-backend

Deployed on Heroku: https://codecoach-marvel.herokuapp.com/swagger-ui/index.html?configUrl=/v3/api-docs/swagger-config

Switchfully final project CodeCoach-backend
CodeCoach Application

The final project of your Switchfully journey will consist of building the CodeCoach application. The idea of CodeCoach application is based on You-Coach (HISTORY.md) and aims to facilitate the peer-to-peer coaching sessions between professional programmers.
!!Warning (1)!!

Stories can change during the project
!!Warning (2)!!

Some screenshots, stories and descriptions will contain references to You-Coach. (Student, school, year, grade, ...) CodeCoach does not focus on students, but on software developers in a professional context. These historical references can safely be replaced.
Timing and agenda

    Kickoff (10/5)

    Sprint 1 (10/5 - 17/5)
        At the end of the sprint we expect from you:
            A Retrospective
            No Sprint Review! However, we expect a Sprint Report. Which should contain:
                Your Commitment (the stories you planned to do). Don't forget the story points.
                The Result (the stories you actually did). Don't forget the story points.
                Your system context diagram
                The result of your retrospective

    Sprint 2 (18/5 - 21/5)
        During this sprint you'll get a short presentation on documentation.
        At the end of the sprint we expect from you:
            A working application in production (Heroku and/or Netlify)
            A Sprint Review (Demo)
            A Sprint Report: the same as last time but now a container diagram should also be added
            A Retrospective

    Sprint 3 (25/5 - 28/5)
        During this Sprint Raf of SPF Finance will give a presentation on architecture.
        At the end of the sprint we expect from you:
            A working application in production
            A Sprint Review (Demo)
            A Sprint Report: the same as last time but now with your database model added.
            A Retrospective

    Sprint 4 (31/5 - 07/6)
        During this sprint you'll get a short presentation on BDD-Testing.
        At the end of the sprint we expect from you:
            !!This will be presented to your future employer!!
            A working application in production
            A Sprint Review (Demo)
            A Sprint Report: the same as last time
            A Retrospective


This project is split in two the youcoach-backend and the youcoach-frontend.

The frontend supports following features:

    bootstrap
    jwt-token based login

Bootstrap

    Bootstrap is used as css framework but is not required to be used.
    The mockups are based on angular-material. So you can always switch to that framework

JWT-tokens

    The login component is setup that it will do a POST call with the username and body.
    The response will contain a header with a JWT-token.
    This token will be saved in your session.
    All other calls to the backend need to contain this JWT-token otherwise the call will be not authorized.
    An interceptor is made so that, if available, your JWT-token will be automatically attached to every http call.
    All this is managed in the authentication directory. Normally nothing in this directory needs to be changed (unless we made an oupsy).

Youcoach-backend

The backend is written in Spring-Boot with JWT-token security written in Spring Security.
JWT-token

Security protocol that avoid sending username+password for every request. Implementation is copied from project-jericho in track-java/security. Normally you shouldn't have to touch the classes in the jwt-package.
User package

Used for user authentication. You should have at least have all the users defined in secured-users. You can used the SecuredUserRepositoryFromJson to load the json file.

In the final version of your project you should manage your users in the database.
Authorization package

Basic authorization package used for mapping roles to features. This whole package can be modified.
High level analysis

Before the start of the project we typically conduct a High Level Analysis (HLA) phase. The goal of this phase is to provide just enough upfront analysis to start the project without defining the complete blueprint of the application.
C4 model

In order to communicate about the architecture of the applications we've chosen to use the C4 Model (Simon Brown). The diagrams below are a materialization of ou HLA phase. Feel free to challenge.
Context diagram
Container diagram

TO DO
Component diagram

TO DO
Class diagram

TO DO
Non-functional requirements
Project constraints

    Follow the SCRUM framework
        Project kickoff
        Sprint kickoff
        Daily standup (rotating SCRUM master role)
        Backlog refinement sessies
        Sprint review (Sprint backlog overview + Demo)
        Retrospective
    Deliverables (Physical or digitized)
        Project backlog (up to date!) (user stories, technical tasks, ...)
        Sprint backlog (estimated + commitment)
        A clean Scrum board (sprint backlog, user stories, technical tasks, story leads/pairs, impediments, ... )
        Definition Of Done
        Evolving Domain model
        C4 model (Context, Container, Component)
        A build monitor dashboard

Technology constraints

    Create a new GitHub repository
        Think about the files Git should ignore, do this before making your first commit...
    Provide a REST(ful) web API (with JSON as the message / body format)
    Use Spring Boot (latest release)
    Use Maven
    Setup a Jenkins or GitHub Actions for continuous integration
        We'll help you with this (but first give it a try, it's really up to you to configure it!)...
    Perform logging (use spring-boot-starter's logging dependencies: logback and slf4j)
        Certainly log all interactions with the application that can be defined as "errors"
            E.g.: unauthorized access, illegal arguments, exceptions in general,...
    Include OpenAPI/Swagger using Springdocs to provide a readable documentation/manual of your REST(ful) web API
    use JPA (Hibernate or EclipseLink) in combination with a PostgreSQL database to store and access the data.
        Setup a proper test configuration, which runs the integration tests against an in-memory database (e.g. H2)
            Make it a separate technical story.
        Correctly setup and handle the transactions.
        Write your DDL (create tables,...) in a separate .sql file, which you also put under version control.
    Think about security (Basic Auth. or JWT), but is doesn't have to be a priority.
    Use materialize CSS and Angular for the front-end
