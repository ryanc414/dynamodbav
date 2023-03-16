[![Go Reference](https://pkg.go.dev/badge/github.com/ryanc414/dynamodbav.svg)](https://pkg.go.dev/github.com/ryanc414/dynamodbav)

dynamodbav - DynamoDB Marshal/Unmarshal utilities
=================================================

Intended as a complement to the official AWS SDK V2 for Go, this micro library
provides marshal/unmarshal helpers using Go 1.18+ generics to reduce boilerplate.

As an example, here is how the following code using the SDK may be simplified
using this package:

```
    // Using SDK directly
    result := new(MyType)

    if err := attributevalue.UnmarshalMap(item, result); err != nil {
        return nil, err
    }

    return result, nil

    // Using this package, reduce 5 lines of code to 1:
    return dynamodbav.UnmarshalItem[MyType](item)
```

