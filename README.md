"""
Overview
========

A small but useful tool to parser mysql slow query

contact: qingqibai@gmail.com

Usage summary
=============

You need to install python-sqlparse to run this tool

you may:

```
    apt-get install python-sqlparse
```

or:

```
    apt-get install python-sqlparse
```

How to use mysql-slow-query-parser to parser slow query::


```
    You can get help with ./parser -h or ./parser --help
    ./parser -f /var/log/mysql/slow-query.log (this will parser the last two hours slow query)
    tail -n2000 /var/log/mysql/slow-query.log|./parser (this will parser the lastest 2000 lines slow query)
    ./parser -f /var/log/mysql/slow-query.log -b'130811 13' -e'130811 15' -sa
    ./parser -f /var/log/mysql/slow-query.log -b'130818' -e'130809' -sc
    parser.add_argument("-f", "--log-file", type=str, nargs="?", help="the mysql slow query file", default=None)
    parser.add_argument("-b", "--begin-time", type=str, nargs="?", help="the begin time to parse", default=None)
    parser.add_argument("-e", "--end-time", type=str, nargs="?", help="the end time to parse", default=None)
    parser.add_argument("-t", "--tmp-file", type=str, nargs="?", help="the tmp file", default='/tmp/mysql-slow-query-parse')
    parser.add_argument("-s", "--sort", type=str, help="sort method, c: count; t:average time; a:c*t", default='c')
    -f or --log_file: the mysql slow query log you want to parser
    -b or --begin-time: the begin time to parse, if not set, it will start at two hours ago
    -e or --end-time: the end time to parse, if not set, it will parse to now
    -t or --tmp-file: the tmp file, default /tmp/mysql-slow-query-parse
    -s or --sort: sort method, c: sort by count desc, t:sort by averger query time desc,
                  a: sort by c*t desc; default c
```
