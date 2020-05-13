# Erlang Samples

These samples were gotten from [here](https://erlangbyexample.org/). For this instance, the 'scone-erlang' image found on docker-images folder is used, but it could be done in either image just changing the tag.

## Running a sample

For example, to load and run `links` module:

```bash
$ docker run -v $PWD:/app -w /app --rm -it sconecuratedimages/experimental:erlang-22.3.2

2020-04-20 00:25:16.892978 Error in process ~p with exit value:~n~p~n
	<0.52.0>
	{epipe,[{erlang,open_port,[{spawn,"inet_gethost 4 "},[{packet,4},eof,binary]],[]},{inet_gethost_native,run_once,0,[{file,"inet_gethost_native.erl"},{line,140}]}]}
erl_child_setup: failed with error 9 on line 162
erl_child_setup: failed with error 9 on line 162
Erlang/OTP 22 [erts-10.7.1] [source] [64-bit] [smp:4:4] [ds:4:4:10] [async-threads:1]

=ERROR REPORT==== 20-Apr-2020::00:25:16.892978 ===
Error in process <0.52.0> with exit value:
{epipe,[{erlang,open_port,
                [{spawn,"inet_gethost 4 "},[{packet,4},eof,binary]],
                []},
        {inet_gethost_native,run_once,0,
                             [{file,"inet_gethost_native.erl"},{line,140}]}]}

Eshell V10.7.1  (abort with ^G)
1> c(links). <= This command compile and load the module
links.erl:2: Warning: export_all flag enabled - all functions will be exported
{ok,links}
2> links:run().
I (grandparent) have pid <0.86.0>
I (parent) have pid <0.87.0>
I (child) have pid: <0.88.0>
I (grandparent) have a linked child: <0.87.0>
I (parent) have a linked child: <0.88.0>
I (parent) have another linked child: <0.89.0>
I (child) have pid: <0.89.0>
I (parent) have another linked child: <0.90.0>
I (child) have pid: <0.90.0>
I (parent) have another linked child: <0.91.0>
I (child) have pid: <0.91.0>
I (parent) have another linked child: <0.92.0>
I (child) have pid: <0.92.0>
I (child <0.88.0>) will die now!
I (child <0.92.0>) will die now!
I (child <0.89.0>) will die now!
I (child <0.90.0>) will die now!
I (child <0.91.0>) will die now!
I (parent) have a dying child(<0.88.0>). Reason: normal
I (parent) will die too ...
I (grandparent) have a dead child(<0.87.0>). Reason: normal
I (grandparent) will die too ...
ok
3> ^G
User switch command
 --> q
```

Reference: https://erlang.org/doc/man/c.html
