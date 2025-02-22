# python-graphql-client
Simple GraphQL client for Python 2.7+

## Install

```sh
pip install graphqlclient
```

## Usage


```py
from graphqlclient import GraphQLClient

client = GraphQLClient('http://graphql-swapi.parseapp.com/')

result = client.execute('''
{
  allFilms {
    films {
      title
    }
  }
}
''')

print(result)
```

### Authorization

Authorization tokens can be added to the request using the client's `inject_token` method:

```py
client.inject_token('very-long-and-secure-token')
```

which defaults to http header name `Authorization`.
An alternative http header name for the token can be set by passing in the alternative header name, e.g. for `x-api-key`:

```py
client.inject_token('very-long-and-secure-token','x-api-key')
```

If you need more options for headers use

```py
client.inject_headers({'your_custom_header_name' : 'your_custom_header_value' ,
                       'your_custom_header_name_2' :'your_custom_header_value_2'})
```

## License

[MIT License](http://opensource.org/licenses/MIT)
