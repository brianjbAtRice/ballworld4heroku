# Team members (Name and NetID):
1. *[Name, NetID]*
2. *[Name, NetID]*
3. *[Name, NetID]*
4. *[Name, NetID]*
5. *[Name, NetID]*
6. *[Name, NetID]*
7. *[Name, NetID]*
8. *[Name, NetID]*

===========================================================
# Notes

This project is configured for React plus Typscript plus a SparkJava backend.   React is designed for "single page applications" 
where the user interface is generated and mutated dynamically rather than navigating to completely 
new web pages for every action.

The project, as cloned, is a fully operational React + SparkJava application that uses 
bidirectional, asynchronous JSON message passing via a websocket connection. 

## As-cloned application features: 

* Available types to add (Fully operational inheritance-based balls as well as update strategies, once implemented):
    * `Diagonal` (pre-loaded for inheritance-based balls) -- Moves in a straight diagonal direction. 
    * `Horizontal` -- Moves in a horizontal direction.
    * `Vertical` -- Moves in a vertical direction.
    * `ColorChanging` -- Changes to random colors.
    * `Curving` -- (pre-loaded for strategy-based balls) Moves in a curving direction.
    * `Wander` -- Moves in a randomly changing directions.
    * `Queen` -- Moves in randomly changing directions but also makes smaller `Child` balls that follow it around.  `Child` balls have a random lifespan and their Queen mother ball will flash random colors when they die.
    * At least two additional ball types of your own design that are completely different than the above types.   Their filenames names should be of the form `XXXBall.java`.

===========================================================
# IMPORTANT: Configuring the project for its first use with React

*See the Using React page in Canvas for complete instructions!*

1. From a terminal window, run `npm install`
    * This will create an `node_modules` folder filled with many, many libraries.
2. Right-click the `src_java/main/java` folder and select `Mark Directory as.../Sources Root` 
3. Likewise, make sure that the `build` and `target` folders are marked as `Excluded`.

===========================================================
# Compiling the React frontend 

In a Terminal window, perform a Production Build by running `npm run build`

***This MUST be done EVERY TIME the React frontend code is changed!***

It is *highly* recommended that you create an IntelliJ Run Configuration for performing a Production Build. 
This will enable a single click on the top bar of IntelliJ to perform the build.   See the Canvas page on 
"Using React" for instructions on how to create a run configuration.

===========================================================
# Running the project locally

*See the Using React page in Canvas for complete instructions!*

## Full testing of the front and back ends (React + SparkJava)

1. If the React/Javascript code has changed, perform a Production Build by running from a terminal tab or if a run configuration was made: `npm run build`
    *  This will compile the React(JSX)/Typescript code down to regular Javascript and bundle it into the `build` folder.
2. Go to the `src_java/main/java/edu.rice.comp610/controller` folder and run the `Controller` class's `main()` method

This will run _both_ the front and back ends using SparkJava's Jetty server.

## Testing just the front-end using the NodeJS dev server

This technique is for a quick test to see if the front-end is rendering properly. 
*This process does NOT create a production build!*

From the IntelliJ Terminal tab or from the run button at the top of the IntelliJ window, run:

    `npm start`

This will run _just_ the React front end using the local NodeJS server.   Expect any functionality that
involves the backend, e.g. websockets, not to work properly.


## Testing just the production build front-end using the NodeJS dev server

This technique is for a quick test to see if the prodution build front-end is rendering properly.

From the IntelliJ Terminal tab or from the run button at the top of the IntelliJ window, run:

First time only to install the production build server:  `npm install -g serve`

To run the production build server: `serve -s build`

## Running the React Components Demo application

The provided React code includes a fully operational demo application that shows examples of using the
provided Ract Components libraries.

To run the demo, simply run one's main application as normal and then go to the following URL relative 
to the root of the application:  `/#/provided/demo`

For example, if running locally, go to http://localhost:4567/#/provided/demo
(Or http://localhost:3000/#/provided/demo if using using the local NodeJS server run from `npm start` or `serve -s build`.)