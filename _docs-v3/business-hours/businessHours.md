---
title: businessHours
since_version: 2.2
---

Emphasizes certain time slots on the calendar. By default, Monday-Friday, 9am-5pm.

<div class='spec' markdown='1'>
boolean / object / array. *default*: `false`
</div>

If `true`, the default business hours will be emphasized ([view live demo](businessHours-demo)). If `false` (the default), there will be no emphasis.

An object may be given to render business hours with fine-grain control over the days/hours. The object may have any of the following properties:

```js
businessHours: {
  // days of week. an array of zero-based day of week integers (0=Sunday)
  dow: [ 1, 2, 3, 4 ], // Monday - Thursday

  start: '10:00', // a start time (10am in this example)
  end: '18:00', // an end time (6pm in this example)
}
```

Alternatively, business hours can be declared with an array. Furthermore, you may define them in parts for additional control (added in v2.9.1):

```js
businessHours: [ // specify an array instead
  {
    dow: [ 1, 2, 3 ], // Monday, Tuesday, Wednesday
    start: '08:00', // 8am
    end: '18:00' // 6pm
  },
  {
    dow: [ 4, 5 ], // Thursday, Friday
    start: '10:00', // 10am
    end: '16:00' // 4pm
  }
]
```

If you are using one of the resource views from the [Scheduler plugin](scheduler), you may specify business hours on a per-resource basis. See the [Resource Object](resource-object) docs for more information.

More information on specifying times can be found in the [Duration](moment-duration) article.
