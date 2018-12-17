# HighConcurrenceToolsTree
并发工具技术研究


![](https://i.imgur.com/UYX1ri0.png)

同步器：

<pre>
等待多线程完成，线程同步

CountDownLatch

      CountDownLatch类:
                方法:  countDown()
                       await()

      Thread 类:
                方法： join

             static CountDownLatch c = new CountDownLatch(2)
</pre>

<pre>
CyclicBarrier

      同步屏障，它要做的就是让一组线程到达一个屏障时被阻塞，直到最后一个线程到达屏障时，屏
   障才会开门，所有被屏障拦截的线程才会继续运行。

      CyclicBarrier类：
                方法： await()

           static CyclicBarrier c = new CyclicBarrier(2);

      应用场景：
              可以用于多线程计算数据，最后合并计算结果的场景，
</pre>

<pre>
Semaphore

       信号量，是用来控制同时访问特定资源的线程数量，它通过协调各个线程，以保证合理的使用
     公共资源。

       private static Semaphore s = new Semaphore(10);

       Semaphore类方法：

                s.acquire();

                s.release();
</pre>

<pre>
Exchanger

       可以在两个线程之间交换数据，只能是2个线程，他不支持更多的线程之间互换数据。

       final Exchanger exchanger = new Exchanger();

       exchanger.exchange(data1)
</pre>


同步容器：

<pre>
    Vector/Hashtable
    ConcurrentHashMap
    CopyOnWriteArrayList
    ConcurrentLinkedQueue
    LinkedBlockingQueue
</pre>