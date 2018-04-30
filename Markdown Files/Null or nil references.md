# Null/nil references

## Does the language use null or nil?

### Objective C 
`nil` for empty object references, `NULL` is for empty void pointers.
### Swift
`nil` is used exclusively in Swift.
## Does the language have features for handling null/nil references?

### Objective C 
Not really. Just use if blocks to check if a value is equal to `nil`. 
### Swift
Swift has optionals to avoid `nil` value exceptions. An variable or field cannot contain a `nil` value unless it is declared as an optional, denoted by a `?` after the type. An optional usually needs to be unwrapped, or check if its value is equal to `nil`, to be used.  
[Back to README.md](/README.md)
