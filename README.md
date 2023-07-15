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
The supported methods and properties to use in Construct 3's scripting feature with the Process object `(v4.0.0.0)`.
For the detailed description and usage of the methods and properties, please refer to the [official object documentation](https://www.constructcollection.com/construct-game-process).

#### Globals
- Context - retrieve the current instance of the Process object.

#### Actions
- addTask(taskName, functionName = null, taskOrder = "async")
  - `task` - the name of the target task from the process.

  **Optional:** If set, this will add a special task with a task function and custom running order. Otherwise, this will only add an asynchronous task without a task function.

  - `func` - the name of the task function which fires on task activation. [Optional]
  - `order` - the order in which to activate a task, including firing the task function. [Optional: Defaults to `async`.]
     - `"start"` - will run synchronously at the start. The process will wait for the earlier `start` tasks to finish before activating the next one.
     - `"async"` - will asynchronously run all tasks at once without waiting for the earlier `async` tasks to finish. The list of `async` tasks will only activate after all `start` tasks have finished.
     - `"end"` - will wait for all `start` and `async` tasks to finish before going through the `end` tasks. The `end` tasks will run synchronously at the end, the process will wait for the earlier `end` tasks to finish before activating the next one.
- setTaskProgress(taskName, processName, percentage)
- startProcess(processName)
- stopProcess(processName)

#### Conditions
- isProcessing(processName)
- hasTask(taskName, processName)
- hasTaskFunction(taskName, processName)
- isTaskRunning(taskName, processName)
- isTaskCompleted(taskName, processName)
- isProcessCompleted(processName)

#### Expressions
- currentProcess
- currentTotalProgress
- currentTask
- currentTaskProgress
- getCurrentTaskOfPorcess(processName)
- getTaskProgress(taskName, processName)
- getTaskFunctionName(taskName, processName)
- getTotalProgress(processName)

### Support
- [Website](https://www.constructcollection.com/)
- [Support Channels](https://www.constructcollection.com/support)
- [Discord Community](https://discord.com/invite/eS3HK88)
- [Construct Forum](https://www.construct.net/en/forum/construct-3/plugin-sdk-10/construct-master-collection-139046)
- [Pricing](https://www.constructcollection.com/pricing)
- [Order Features](https://www.constructcollection.com/order)
