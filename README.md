# API concept

Proposal and workflow for developing APIs using lowcode to code.

First define API using Weblang:

```yml
action: /account/create
filters:
  - require_login
  - require_account
  - require_admin
validate:
  query: 
    id:
      is: id
      min: 2
$result:
  @db:
    path: account/get
    query: $params.query
    
@return: $result
```

The tests for this will be automatically generated.

If you want to transition some actions to code, the tests will still work.

Discuss: Do you really need tests if the code is this simple?

