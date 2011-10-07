## Simple OTP Application using Rebar

A simple OTP application generated using rebar.

1. Download and compile Rebar

    hg clone ssh://hg@bitbucket.org/basho/rebar

2. Compile the SampleApp

    >$ rebar compile
    >
    >==> mysample_app (compile)
    >
    >Compiled src/mysample_app.erl
    >
    >Compiled src/mysample_sup.erl
    >
    >Compiled src/mysample_server.erl
    >
    >==> rel (compile)
    >
    >==> otp_rebar_sample (compile)

3. Create a rebar release

    $ rebar generate
    ==> rel (generate)

4. Make the application executable

    >$ chmod u+x rel/mysample/bin/mysample
    >
    >$ ./rel/mysample/bin/mysample
    >
    >Usage: mysample {start|stop|restart|reboot|ping|console|attach}

5. Startup the application

    >$ ./rel/mysample/bin/mysample console
    >
    >...
    >
    >Eshell V5.8.4  (abort with ^G)
    >
    > (mysample@127.0.0.1)1>

6. Check everything works

    >(mysample@127.0.0.1)1> application:which_applications().
    >
    >[{mysample_app,[],[]},
    >
    >{sasl,"SASL  CXC 138 11","2.1.9.4"},
    >
    >{stdlib,"ERTS  CXC 138 10","1.17.4"},
    >
    >{kernel,"ERTS  CXC 138 10","2.14.4"}]
    >
    >(mysample@127.0.0.1)2> mysample_server:start_link().
    >
    >{ok,<0.54.0>}
    >
    >(mysample@127.0.0.1)3> mysample_server:say_hello().
    >Hello from server!
    >ok

### Resources:
Some useful resources for understanding Rebar:

* [Rebar on BitBucket](https://bitbucket.org/basho/rebar/wiki/Home)
* [Erlang Application Management with Rebar](http://alancastro.org/2010/05/01/erlang-application-management-with-rebar.html)
* [Erlang Rebar Tutorial - Generating Release Upgrades](http://www.metabrew.com/article/erlang-rebar-tutorial-generating-releases-upgrades)

