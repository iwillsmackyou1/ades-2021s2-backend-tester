# ADES AY2021 Sem2 Backend Tester

## Grading Instruction

1. Set Database Connection Strings
   1. 2B01: postgres://mursjkwp:r6KXybdnpd2g8glGoHkNRDigGZ_vPNVu@john.db.elephantsql.com:5432/mursjkwp
   2. 2B02: postgres://rkarncql:7skaXpRwicO-6QQwwUzpSIZF81hhTrhQ@john.db.elephantsql.com:5432/rkarncql
   3. 2B03: postgres://yjnhhwlu:OuA19kUSLYZDig5T6DaRHvtVskwdjSW6@john.db.elephantsql.com:5432/yjnhhwlu
   4. 2B04: postgres://jkiyfzqg:qHsHqSC6x9wRpHUy77qP7WIUW03-4ShV@john.db.elephantsql.com:5432/jkiyfzqg
2. Start Customer Instance
   1. `npm run start-win-customer`
   2. `npm run start-macos-customer`
        > Permission Denied? Run: chmod +x ./bin/www-macos
3. Awake Heroku (Just open the link in browse)
   1. 2B01: http://ades-2b01.herokuapp.com/
   2. 2B02: http://ades-2b02.herokuapp.com/
   3. 2B03: http://ades-2b03.herokuapp.com/
   4. 2B04: http://ades-2b04.herokuapp.com/

## First things first - Set database connection

1. Go to elephantSql and copy the connection string of any instance.
2. Set the database connection string in `.env` file.

## Running an instance for CUSTOMERS

> Customer instance uses port 3000 and have 4 database connection to handle high load from customers joining queues
>
> The mobile app should connect to this instance.
>
> The script to simulate customers joining queue uses this instance too.

1. Windows

    ```
    npm run start-win-customer
    ```

2. MacOS

    ```
    npm run start-macos-customer
    ```

3. Linux

    ```
    npm run start-linux-customer
    ```

## Running an instance for COMPANY

> Company instance uses port 8080 and have 1 database connection only
>
> The Website should connect to this instance.

1. Windows

    ```
    npm run start-win-company
    ```

2. MacOS

    ```
    npm run start-macos-company
    ```

3. Linux

    ```
    npm run start-linux-company
    ```

## Simulating Customers joining queue

1. Start an backend instance for CUSTOMER

2. Create Queues in the backend

    ```
    npm run populate-website
    ```

3. Single Peak Scenario

    > Company Id: 1000000001; Queue Id: QUEUE01001

    ```
    npm run single-peak
    ```

4. Double Peak Scenario

    > Company Id: 1000000001; Queue Id: QUEUE01002

    ```
    npm run double-peak
    ```

5. Sustained Peak Scenario

    > Company Id: 1000000001; Queue Id: QUEUE01003

    ```
    npm run sustained-peak
    ```
