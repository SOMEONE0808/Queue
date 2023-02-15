# API

## Global Methods

### QueueModule.new
    QueueModule.new(name: any, DebugMode: boolean) -> Queue
Create [Queue](https://someone0808.github.io/Queue/api/#queue-api) instance<br/>
if name is **nil**, the queue will not have any name

## Queue API

### Queue:Add
```lua
Queue:Add(parameters: table, callback, noActivate: boolean) -> queueId
```
Add task to queue<br/>
if **noActivate** is true, it will not do **Queue:ActivateAsync()**

### Queue:Expire
```lua
Queue:Expire(queueId: number) -> queueId or -1
```
Expire queue which id is **queueId**<br/>
if it can't find queue with id is **queueId**, it returns **-1**

### Queue:Wait
```lua
Queue:Wait(length: number)
```
Stop queue for **length** sec<br/>
if **length** isn't number, queue will stop until activated

### Queue:Activate
```lua
Queue:Activate(activateId: number)
```
Activate queue

### Queue:ActivateAsync
```lua
Queue:ActivateAsync(activateId: number)
```
Activate queue without yielding