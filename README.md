# modules-and-tests-golang

This example implements a basic example of how to create your own modules, and how to call them from other modules. In addition, an example of how to do unit tests is developed.

## Setting

Edit the example.com/hello module to use your local example.com/greetings module.

From the command prompt in the hello directory, run the following command:

```sh
go mod edit -replace example.com/greetings=../greetings
```

The command specifies that example.com/greetings should be replaced with ../greetings for the purpose of locating the dependency.

Now, from the command prompt in the hello directory, run the go mod tidy command to sync the example.com/hello module dependencies, adding those required by the code, but not yet tracked in the module.

```sh
go mod tidy
```

The command found the local code in the greetings directory, then added a require directive to specify that example.com/hello requires example.com/greetings.

Done, now you can work with the example
