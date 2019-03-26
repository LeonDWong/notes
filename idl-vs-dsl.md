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

```java
namespace cpp thrift.example
namespace java thrift.example

enum TweetType {
    TWEET,
    RETWEET = 2,
    DM = 0xa,
    REPLY
}

struct Location {
    1: required double latitude;
    2: required double longitude;
}

struct Tweet {
    1: required i32 userId;
    2: required string userName;
    3: required string text;
    4: optional Location loc;
    5: optional TweetType tweetType = TweetType.TWEET;
    16: optional string language = "english";
}

typedef list<Tweet> TweetList

struct TweetSearchResult {
    1: TweetList tweets;
}

exception TwitterUnavailable {
    1: string message;
}

const i32 MAX_RESULTS = 100;

service Twitter {
    void ping(),
    bool postTweet(1:Tweet tweet) throws (1:TwitterUnavailable unavailable),
    TweetSearchResult searchTweets(1:string query);
    oneway void zip()
}
```