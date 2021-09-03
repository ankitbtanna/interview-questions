# TypeScript Interview Questions

## What is the latest version/features in TypeScript?
- v4.4
- Features
    - Control Flow Analysis/TypeGuard Variables typeof a === string
        - behavior on type of variable
        ```
        const double = (arg: string | number) => {
        if (typeof arg === 'string') {
            return `${arg} - ${arg}`;
        } 

        if (typeof arg === 'number') {
            return arg * 2;
        }

        return arg;
        }
        ```

        ```
        const double = (arg: string | number) => {
            const isString = typeof arg === "string";
            const isNumber=  typeof arg === "number";	

            if (isString) {
                return `${arg} - ${arg}`;
            } 

            if (isNumber) {
                return arg * 2;
            }

            return arg;
        }
        ```
    - Defaulting to the unknown Type in Catch Variables --useUnknownInCatchVariables
    ```
    try {
    executeSomeThirdPartyCode();
    }
    catch (err) { // err: unknown
        // Error! Property 'message' does not exist on type 'unknown'.
        console.error(err.message);

        // Works! We can narrow 'err' from 'unknown' to 'Error'.
        if (err instanceof Error) {
            console.error(err.message);
        }
    }
    ```
    - Exact Optional Property Types --exactOptionalPropertyTypes
    ```
    interface Person {
        name: string,
        age?: number;
    }

    // The above interface actually means
    interface Person {
        name: string,
        age: number | undefined;
    }
    
    interface Person {
        name: string,
        age?: number;
    }

    // Valid
    const person1 = {
        name: 'Dries'
    }

    // Also valid
    const person2 = {
        name: 'Alistair',
        age: 16
    }

    // Not valid
    const person3 = {
        name: 'Harrison',
        age: undefined, // Age is not a number!
    }
    ```

