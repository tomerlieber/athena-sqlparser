# Athena SQL Parser

Go package for parsing Athena SQL SELECT statements and queries on views.

It's a fork of https://github.com/blastrain/vitess-sqlparser that is designed to do the same but for MySQL.

Note that MySQL is different from Athena. For example, double quotes are used around table and column identifiers in Athena SQL and around strings in MySQL.


# Installation

## [NOTE] Required Go version more than 1.9

```
go get -u github.com/tomerlieber/athena-sqlparser
```

# Examples

```go
package main

import (
 	"fmt"
	"github.com/tomerlieber/athena-sqlparser/sqlparser"
)

func main() {
	stmt, err := sqlparser.Parse("select * from user_items where user_id=1 order by created_at limit 3 offset 10")
	if err != nil {
		panic(err)
	}
	fmt.Printf("stmt = %+v\n", stmt)
}

```
