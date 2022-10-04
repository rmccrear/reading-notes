# Event Driving Programming

Node as a library called events that has the EventEmitter class.
You can use it like this:

    const {EventEmitter} = require('events');
    const sandwichHotline = EventEmitter();

    sandwichHotline.on('order', (order) => {makeSandwich(order)});

    sandwichHotline.emit('order', {type: "Rueben"});


This will call the makeSandwich function everytime you call

    sandwichHotline.emit('order', {type: "Rueben"});

## Event Driving Programming and OOP

One nice thing about this paradigm is that an object can handle its own responsibilities once an event occurs. As long as the object has access to the EventEmitter, it can respond to events in a very predictable way. It's a good way for two objects to communicate with each other without getting too intertwined. For example, the Waiter can take the order and the Chef can make the order.

    
    const {EventEmitter} = require('events');
    const orderEmitter = new EventEmitter();

    class Chef{
        constructor(orderEmitter){
            orderEmitter.on('order', (order) => this.makeOrder(order));
        }
        makeOrder(order){
            console.log("Working on it...")
            // ...
        }
    }

    class Waiter{
        constructor(orderEmitter){
            this.orderEmitter=orderEmitter;
            orderEmitter
        }
        takeOrder(order){
            console.log("Taking order...");
            this.orderEmitter.emit('order', order);

        }
    }
    
    const chef = new Chef(orderEmitter);
    const waiter = new Waiter(orderEmitter);

    waiter.takeOrder({type: "Rueben"});
    // Output:
    // Taking order...
    // Working on it...

The Waiter and the Chef classes don't need to have access to each other except through the orderEmitter. This helps to keep them separate.
