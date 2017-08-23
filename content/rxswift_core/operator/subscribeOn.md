## subscribeOn

**指定 `Observable` 在那个 `Scheduler` 执行**

![](/assets/Operator/Operators/subscribeOn.png)

**ReactiveX** 使用 [Scheduler] 来让 `Observable` 支持多线程。你可以使用 **subscribeOn** 操作符，来指示 `Observable` 在哪个 [Scheduler] 执行。

[observeOn] 操作符非常相似。它指示 `Observable` 在哪个 [Scheduler] 发出通知。

![](/assets/Operator/Operators/schedulers.png)

默认情况下，`Observable` 创建，应用操作符以及发出通知都会在 `Subscribe` 方法调用的 [Scheduler] 执行。**subscribeOn** 操作符将改变这种行为，它会指定一个不同的 [Scheduler] 来让 `Observable` 执行，[observeOn] 操作符将指定一个不同的 [Scheduler] 来让 `Observable` 通知观察者。

如上图所示，**subscribeOn** 操作符指定 `Observable` 在那个 [Scheduler] 开始执行，无论它处于链的那个位置。 另一方面 [observeOn] 将决定后面的方法在哪个 [Scheduler] 运行。因此，你可能会多次调用 [observeOn] 来决定某些操作符在哪个线程运行。

[Scheduler]:/content/rxswift_core/schedulers.md
[observeOn]:observeOn.md