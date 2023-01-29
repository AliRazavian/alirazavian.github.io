# AI: The Next Generation of Software

Since the 1940s and 1950s, computer scientists have developed two philosophies for creating smart machines: telling the machine what to do, and showing the machine what to do.

The first philosophy led to rule-based systems, and software as we call it today. The peak of this philosophy was when IBM’s Deep-Blue defeated Garry Kasparov in Chess. IBM wanted to brag about how advanced their AI was, but ironically that was when most people lost their interest in rule-based systems as the way to achieve intelligence.

The second developed into machine learning, or Software 2.0. There’s a fundamental difference between the two approaches, and a paradigm shift is coming.
Why should businesses care about Software 2.0?
Photo by nicolettec on Pixabay

The difference between the philosophy of Software 1.0 and Software 2.0 leaves significant practical implications: complexity.

With traditional software, every time an “IF” statement is written, the process splits into two possible threads, and the complexity of the code doubles. The complexity of the code grows exponentially to the lines of codes and it becomes exponentially harder to debug.

Then what do businesses do to resolve this complexity? They hire more developers to handle the complexity of the code. But more developers mean more codes meaning exponentially more complexity to the point that the business reaches the limits of its hiring capacity. For small companies, this limit could be 10–100 developers and for a company as rich as Google this number is around 100,000 developers.

So what happens when a company reaches its limit of hiring new developers? Well, creativity dies. Companies fail to create because all their resources go to maintaining and debugging the entangled code-base they already have.

To give an example, have you noticed that almost every product that Google has come up with that has more than a Billion users came out before 2008? (Search, Gmail, YouTube, Maps, Android, Chrome, etc). And all of them reached a billion users relatively quickly. But anything that they have built after 2008, is either dead, or it has failed to reach a sizable users-base and will likely be terminated soon. Google is failing to create new useful products for the last 14 years because of the complexity of its code-base. Almost all Google employees spend almost all their time moving function calls from one library to another. Libraries and APIs that are designed to unify more products. Products that are too entangled in the complexity of the codebase to ever come out or would die in their infancy.

Every time traditional software fails to do what it is supposed to do, the software must be brought back to the office and debugged there. Software 2.0 however, learns from its mistakes. Every time software 2.0 fails, it automatically learns not to fail the next time.
The quality of software 1.0 improves (or degrades) when the software developer (who holds the entire complexity in their brain) instructs the software to change its behavior. But Software 2.0 improves every time the code is executed.

>With proper use of Software 2.0, businesses could continue to invest their resources in creativity rather than maintaining and debugging what they have. A new revolution in software services is on its way.

# Why is Software 2.0 uncommon?

## 1- Inefficient Hardware

<Photo by analogicus on Pixabay>

The first obvious obstacle is the processing power required to execute these algorithms. Hardware as we know it has evolved side by side of Software. The current processors are extremely good at executing one instruction at a time as fast as possible. This is not in any way efficient for Software 2.0.

With Software 2.0, the wast majority of processing time is spent on one operation: Dot-Product.

The way dot-product is carried out in the existing computers is that first, the processor fetches two elements of a vector into its cache, then multiplies them together, sum them up, and put the results back in the memory. Almost all the time spent calculating a dot-product operation goes to the data transfer.

There have been efforts to put map-reduce inside the memory but map-reduce is too generic and requires expensive processing circuits to be implemented inside the memory. This approach is too expensive to implement. Dot-product however can be implemented inside the memory unit, by introducing a set of capacitors to every memory address and implementing multiplication and addition with smart wiring of capacitors leaking into another.

With this new form of memory, (which is not a random access memory) we can directly read the dot-product of two vectors almost as fast as reading a single value from the vector with extremely low power consumption.

The introduction of Tensor Cores in Nvidia processors and ML cores in Apple processors are indicators that the industry is accepting Software 2.0. Yet, these circuits are still designed in the Von-Neumann architecture.

In the Von-Neumann architecture (which is basically “the” architecture for any type of processing machine ranging from your smart TV to Amazon’s supercomputer) there is a clear distinction between the memory and processor. We can exactly say if a transistor belongs to a processing circuit or a memory circuit. This is not the case for the human brain where it is unclear whether a neuron is a memory or process neuron. In the new architecture, (which to the best of my knowledge does not exist yet) the process of dot-product is migrated into the memory unit. This brings huge efficiencies into the world of Software 2.0

## 2- Lack of Established Processes

<Photo by jarmoluk on Pixabay>

Tomas Kuhn in his book “The Structure of Scientific Revolutions” highlights that the paradigm shift is not a smooth process. Believers of the new paradigm are generally young people who are willing to jump ship while older more experienced ones remain on the old paradigm and disappear from the memories. The industry decision-makers (Product Managers, CTOs, etc…) have at most 30–40 years of experience and to them, everything that has happened in the software world had been an incremental improvement. Software 2.0 or Machine Learning as it is called in academia, branched out from what we call software today almost 80 years ago. It is hard to convince them that the paradigm is shifting.

When developing traditional software, there are four distinct steps to take: Define, Implement, Deploy, and Debug. Software 2.0 however has three different steps: Define, Deploy, and Monitor. There is no implementation or debugging step. Software 2.0 learns automatically as it is deployed. Software 2.0 is no longer developed by the software developers or data scientists, rather by the data that the model is exposed to on the fly and the annotators that are scattered all over the globe.

But neither the process nor the tools for Software 2.0 are well established yet. Every time there is a paradigm shift, there is resistance to it. Given what we see, it is very unlikely that the software 2.0 revolution is led by the silicon valley giants. The next pioneers of Software 2.0 are still in their small startups trying to define what the industry should be.

## 3- knowledge Gap

I mentioned that Software 2.0 learns from its mistake without the need for a software developer. The technology to automate this loop was only invented recently. Deep Learning is at the center of Software 2.0 since it’s the only algorithm capable of achieving super-human accuracy on every family of tasks. (super-human accuracy means the annotators’ accuracy. Which as a group is generally higher than a single individual. Hence the name super-human). DL only began to take off in academia in 2012–2014. The success of Deep Learning in Academia encouraged the industry to copy academic solutions into their pipelines and that lead to disappointment. Three distinct problems need to be solved to automatically achieve superhuman accuracy on real-world data.

### 3–1- Long-tail distribution

<Photo by zoohojakjil on Pixabay>

Let’s start with an intuitive example. Imagine if a person wants to learn about a topic, say quantum physics. And they go to a library to gain that knowledge. They start to randomly pick up a book, read it all the way through, put it back, and pick up another book until all the books in the library are read. Then they repeat this step until every book is read 10–100 times. This is how Deep Neural Networks are trained. This process is extremely redundant. If they read a book about the alphabet after reading a book about quantum physics, well, one of the two books could have been skipped.

Data in nature follows a long-tail distribution. A few observations are common while genuinely new observations are rare. And as the training improves, the number of informative samples drops exponentially. Active Learning is a technique developed decades ago to address this problem but Active Learning relies on the model to tell whether a sample is informative or not. Deep Learning is anything but explainable. Current Deep Active Learning methods marginally outperform random sampling. That means even though the number of informatics samples drops exponentially. Most DAL methods still subsample linearly w.r.t to the dataset size. Hard examples can easily get buried under mountains of easy data points leading to sub-optimal performances.


### 3–2- Ambiguity

Photo by songpon on Pixabay

The information space is continuous: similar phenomena tend to behave similarly. In ML, this hypothesis sometimes appears explicitly (for example when we use a regularizer) and sometimes implicitly (for example if a Laplacian matrix shows up, which it always does in DL analysis). Yet by far, the biggest problem industry has is the classification problem. Classification assumes that the information space is discrete. This discrepancy between our assumptions and the nature of data is another source of error. Tearing the continuity of data space creates shock waves that flow through the entire predicted manifold.

Imagine a video, where in the first frame there is a cat in front of a clean background. The cat-hood of this frame is True. And in the last frame, the cat has left the frame and the cat-hood of the frame is False. At which frame exactly did the cat-hood bit flipped? And if we assume cat-hood is a continuous variable, how does one decide if a frame is 38.3% cat or 38.5%?

There are almost always samples in the gray area. Even worse, since labels follow a long-tail distribution, there are significantly more samples in the gray area than there are in one of the assumed classes.

And there is yet one more problem: In many cases, we are biased to sample more from the gray area. In many NLP applications, fairly obvious events are not worthy of recording. In many medical applications, healthy people rarely take a test, and obviously sick patients participate less in the medical tests than the ones whose conditions cannot easily be determined.

When it comes to real-world data, the observation distribution is likely skewed towards the gray area while the label space assumes data lie in a clean black and white world. The problem definition itself is erroneous. It is not enough that Software 2.0 learns from the data, it should also learn what the right problem definition and observation distribution are.

### 3–3- Inconsistency

Photo by christianpackenius on Pixabay

While ambiguity talks about samples that are neither A nor ~A, Inconsistency is about samples that are both A and ~A. What is the right decision when one doctor recommends a surgical procedure and another thinks non-surgical treatments are the best?

The first bad way of dealing with these samples is to through them away. This (in my experience) is the biggest source of discrepancy between academic and industrial datasets. Another bad way of dealing with inconsistent samples is to use multiple annotators and vote for the label which is also common in academic datasets. Inconsistency is a great source of information. It shows that the decision boundary should be nearby. No other sample reflects that.

Inconsistency has appeared in many forms in academic research. Especially where the teacher is a model and not a human annotator. Self-supervised learning uses inconsistency of a model with itself as a source of information for learning better representation. Some video-analysis pipelines use the inconsistency of the same model on two consecutive frames (flickering predictions) as an indicator to harvest hard examples. Yet to the best of my knowledge no one has published the inconsistency problem in a unified statistical framework.


# A Software 2.0 Interpreter

A while ago, I came across a guideline written in the 1970s addressed to the Ph.D. students and one of the recommendations was to never write your compiler!

I think Software 2.0 is where traditional software was in the 1970s. Even businesses who get the potential of Software 2.0 right, still rewrite the data pipelines and back-propagation algorithms and all of the complexities that everyone else is rewriting. There is a need for a Software 2.0 compiler that can address all the AI problems all businesses have.

In the next article, I’ll write about what components software 2.0 must have to solve most AI problems in the industry. But until then, please allow me to introduce what we are doing. We set out to build this Software 2.0 compiler. We are dedicated to openness and transparency and we plan to opensource our code-base soon. But until then, if you are interested in building this with us, please send a link to your Google Scholar and Github to me at ali@razavian.org
