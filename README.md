# Nube-flows
Nube-iO Node-red Flow's


## HVAC Control Logic

### [2 Stage Compressor Control ](https://github.com/NubeDev/nude-flows/blob/master/HVAC-2StageCompControl.md)

This is a flow for controlling compressor staging


### [Min and Max on/off time delay flow ](https://github.com/NubeDev/nude-flows/blob/master/MinMax%20Time%20Delay.md)

This is a flow for controlling compressor staging




### [Time Schedule Flow ](https://github.com/NubeDev/nube-flows/blob/master/timeScheduleFlow.md)

You need to install moment.js and enable in the settings.js file



### [Convert a timezone in node-red ](https://github.com/NubeDev/nube-flows/blob/master/convertTimeZoneFlow.md)

```
var nDate = new Date().toLocaleString('en-UK', {
    timeZone: 'Australia/Sydney'
});

timeAu = (nDate);

node.status({fill:"blue",shape:"dot",text:"Message recieved:  @" +" "+ timeAu});
return msg;

```

```
const event = new Date();

const options = {
  year: 'numeric',
  day: 'numeric',
  month: 'long',
  weekday: 'short',
  hour: 'numeric',
  minute: 'numeric',
  timeZoneName: 'short',
  timeZone: 'Australia/Sydney',
};

msg.payload = (event.toLocaleString('en-AU', options));


return msg;

```



## Arrow functions (Lambda) in nodejs

```

someValues = [1, 2, 3, 4];

someValues.forEach((element) => {
    node.warn(element);
});

node.warn(someValues.map(x => 8 * x));

```

## Counter

```

if (context.hasOwnProperty("counter"))
	context.counter += 1;
else
	context.counter = 0;

context.flow.counter = context.counter + 1;

msg.payload = "local counter = " + parseInt(context.counter, 10);
node.status({fill:"green",shape:"dot",text:msg.payload});

return msg;

```


