# construct-game-process
The Script Interface documentation for the [Process](https://www.constructcollection.com/construct-game-process) addon of the [Construct Master Collection](https://www.constructcollection.com/), for [Construct 3](https://construct.net/).

## IProcessInstance documentation
This is the documentation to use Construct 3's new JavaScript [Scripting feature](https://www.construct.net/en/make-games/manuals/construct-3/scripting/overview) with the Process object.

### Easy usage
You can easily access the Process object's interface using the `runtime`, from both the event sheet and script.
```JS
runtime.objects.Process.getFirstInstance().startProcess("process");
```
For more information, please see the [scripting documentation of the Sprite object](https://www.construct.net/en/make-games/manuals/construct-3/scripting/scripting-reference/plugin-interfaces/sprite).

### Advanced usage
You can also subclass instances in a script, please see the [subclassing instances documentation](https://www.construct.net/en/make-games/manuals/construct-3/scripting/guides/subclassing-instances) for more information.
```JS
class Process extends IProcessInstance
{
	constructor()
	{
		super();
	}
}
```

### API
The supported methods and properties to use in Construct 3's scripting feature with the Process object.
For the detailed description and usage of the methods and properties, please refer to the [official object documentation](https://www.constructcollection.com/construct-game-process).

#### Globals
- Context - retrieve the current instance of the Process object.

#### Actions
- addTask(task, func, order)
  - `task` - the name of the target task from the process.

  **Optional:** If set, this will add special tasks with a callback function with customizable order. Otherwise, this will only add a regular task without a callback function and will run asynchronously.

  - `func` - the name of the callback function. [Optional: Fill with `order` to add a special task.]
  - `order` - the order in which to run the callback function. [Optional: Fill with `func` to add a special task.]
     - `"async"` - will run all functions without waiting for the other tasks to finish.
     - `"sync-start"` - will wait for the earlier task to finish before calling the next one.
     - `"sync-end"` - will wait for all other tasks to finish before running, synchronously.
- startProcess(process)
- setTaskState(process, task, perc)

#### Conditions
- hasTask(process, task)
- isProcessing(process)
- isCompleted(process)

#### Expressions
- currentTask(process)
- currentPercentage(process)
- currentFunction(process)
- currentProcess()
- totalPercentage(process)

### Support
- [Website](https://www.constructcollection.com/)
- [Support Channels](https://www.constructcollection.com/support)
- [Discord Community](https://discord.com/invite/eS3HK88)
- [Construct Forum](https://www.construct.net/en/forum/construct-3/plugin-sdk-10/construct-master-collection-139046)
- [Pricing](https://www.constructcollection.com/pricing)
- [Order Features](https://www.constructcollection.com/order)
