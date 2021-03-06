## Core

Performance is based on DomHighResTimeStamp (timeOrigin and clock) on calculation. It's helpful for developer to estimate the web performance in browser.

### E.G.

calculate the script execution cost.

```javascript
performance.mark("mySetTimeout-start");

// Wait some time.
setTimeout(function() {
  // Mark the end of the time.
  performance.mark("mySetTimeout-end");

  // Measure between the two different markers.
  performance.measure(
    "mySetTimeout",
    "mySetTimeout-start",
    "mySetTimeout-end"
  );

  // Get all of the measures out.
  // In this case there is only one.
  var measures = performance.getEntriesByName("mySetTimeout");
  var measure = measures[0];
  console.log("setTimeout milliseconds:", measure.duration)

}, 2000);
```

## Other metric

There are more metrics for us to measure our web's performance by using `performance.timing` or `performance.mark` and `performance.measure` to show detail of every phase until content in page is all downlowaded.

### Phase

#### Navigation Timing

| key | desc |
| -- | -- |
|     |      |


#### Resource Timing

#### User Timing





