# Erlang Studies

Erlang is a functional programming language with immutable data, pattern matching, dynamic typing, and hot code loading.

- everything is a process
- processes are strongly isolated
- process creation and destruction is a lightweight operation
- message passing is the only way for processes to interact
- if you know the name of a process you can send it a message
- processes share no resources
- error handling is non-local
- processes do what they are supposed to do or fail (Let it crash)

**Concurrency** came from creating a language to meet the near real-time and fault-tolerant requirements while building distributed telecom applications at Ericsson.

**BEAM** the virtual machine that compiles Erlang into bytecode that it executes. 

**OTP** libraries, middleware, and tools that are part of the Erlang distribution. 

**Versioning of Erlang** can be confusing at first. Erlang/OTP 19.3 was released on March 2017. Prior to that release Erlang used a R-Version scheme. This new scheme uses a `<MAJOR>.MINOR>.<PATCH>` and it is not semver. It can have more than three dot-seperated parts. When all less significant parts are `0`  they're omitted. These additional parts are branches and they [behave differently](https://erlang.org/doc/system_principles/versions.html#order-of-versions).

- `erl` is the Erlang shell that includes a number of [shell](https://erlang.org/doc/man/shell.html) commands.
- `%` are for comments.
- Multiline strings can span multiple lines till the end with a `".`.
- [`Edoc`](http://erlang.org/doc/apps/edoc/chapter.html) to generate documents.
- Variables must begin with a capital letter (CamelCase).
- Variables can only be assigned once. Declaring a variable is a statement of fact.
- Atoms are lower-case (snake_case).
- Module and Function names are atoms.
- Modules in Erlang are like classes in object-oriented languages.
- `spawn` creates a new process for a function defined in a module.
- Erlang can have multiple processes running the module.
- Sending messages using `Pid ! Msg` syntax.
- Functions can be arguments to functions and functions can return functions.
- _high-order functions_ are called a `fun`.
- _list-at-a-time_ operations like `lists:map` or `lists:filter`.
- pattern matching combined with `funs` is used for control structures.
- _list comprehensions_ `[ F(X) || X <- L].`
- _guard sequence_ separated by `;` is `true` if at least one of trhe guards are `true`.
- _guard_ is a series of expressions, separated by `,` and is `true` if all expressions are `true`.
- _guard predicates_
- Use _records_ when the data uses a fixed number of predetermined atoms, number of elements and names of the elements will not change with time, when storage is an issue.
- Use _maps_ for key-value structures when the keys are not known in advance, data with large numbers of different keys, or as a ubiquitous data structure where efficiency is traded-off for convenience, self-documenting data structures, key-value parse trees (XML, config files), communication with other languags using JSON.
- _record_ declarations cannot be used in the shell, declare them in a module or use `rr`.
- record definitions can be in the module source code or in a header file (`*.hrl`).
- records are like `structs` in C.
- records are decalred with a `-record(Name, {key1=Val1, …, keyN=ValN}).` with keys being an `atom`.
- records are created with a `#`. Example: `ExRecord = #record_name{key1=Value1}.`
- _maps_ have a similar syntax to _records_, but without the record name.


[Program Development Using Erlang - Programming Rules and Conventions](http://www.erlang.se/doc/programming_rules.shtml)

[Adopting Erlang](https://adoptingerlang.org/)
[Stuff Goes Bad: Erlang in Anger](http://www.erlang-in-anger.com/)
