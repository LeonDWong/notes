## Preface

**DSL(Domain Specific Language)**: It's designed for common expression for data in multiple language. E.g.: `xml`, `JSON`.

**IDL(Interface Definition Language)**: It's design for API description by data struct language. E.g.: thrift IDL. 

## Example

#### DSL

```xml
<route id="simpleExample">
  <from uri="seda:orders"/>
  <filter>
    <simple>${in.header.foo}</simple>
    <to uri="mock:fooOrders"/>
  </filter>
</route>
```


#### IDL
