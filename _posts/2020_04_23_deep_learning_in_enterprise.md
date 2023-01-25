# Deep Learning in Enterprise for Team Members
## Necessary rules that every deep learning team should follow

Use the right tools for your tasks.

If you are not using the flexibility of these models to your benefit, you are not using deep learning in its full glory, and for that, the choice of libraries you use to train your neural network matters.

> Use ```PyTorch```


PyTorch and TensorFlow are the most commonly used libraries for deep learning. The flexibility and adaptability of PyTorch are unparalleled to any other library I have worked with. Torch and later on, PyTorch was designed by and for the community who developed deep learning itself, and in my opinion, PyTorch is the only library that brings the best of deep learning out. Stating the obvious, a neural net is a mathematical function; if you have to use TensorFlow (for example in your android app), you can train your neural net dynamically on a server in PyTorch and deploy the parameters -which are just a bunch of numbers- to the TensorFlow or Azure back-end of your app.

> Git is not designed to track Software 2.0

So let’s say you have written a source code that trains a Deep Network. Every time you “execute” your training code (Software 1.0), your neural net (Software 2.0) changes. The source code that detects tumors in CT’s is almost identical to the code that detects a pedestrian in a self-driving car’s data feed. The only dataset is different. Git is not designed to keep track of your dataset, your annotation set, or the number of times your code is executed. Currently, DVC is one of the few tools that is designed to keep track of your Software 2.0. If you know a better version control library, please let me know, and I’ll update this article.

>Run your codes in Dockers

Deep learning libraries and tools are not mature yet. Default behaviors change with every major release. Dockers help you preserve your code in time and make sure your code runs two years from now like today.

> Have a dataset compiler if you haven’t already

Data management is the most important unit that has to be built. A dataset compiler is stand-alone software that keeps track of all your data, annotations and predictions (Yes you need to keep track of every model’s predictions as well) and depends on the experiment you are running, it compiles a new dataset for you, that you can deploy on your server for training. I will write a separate post about how this module should look like. Please do let me know if such a module exists with full functionality, and I’ll put a link to it here.

>Intuition comes from your logs

Have a unified tool that manages all your experiment results, hyper-parameters, and logs together. A good visualizer packages all this information together and lets you get the best out of your data and models. I personally like w&b. But there are other bloggers out there too, so pick your favorite.

>Pick the data format that suits your task

```json```, ```yaml```, ```pandas```, and many more libraries provide simple formats for your data. Each has its own plus and minuses. Yaml is slow if your file is too big but easier to modify by hand than JSON. Make sure you understand what your task needs before starting to code.
Measurement is the key.

>If you are not measuring it, you are not improving it

Every time a new task is defined, the first ticket that must be issued is the collection of a ”validation set.” If you don’t know how good or bad your neural net is doing on a task, it is very unlikely that your future efforts would lead to anything fruitful. The validation set must be collected at random and must have the same statistical properties as the domain you are working on.

>Do not cherry-pick the samples in the validation set.

Stating by the validation set, you will know how hard it would be to annotated your training set. How much would that cost and how easy or hard your task would be with very little resources over a short period? My advice is to annotate the validation set yourself AND distribute the annotation task among team members. Look at the disagreements between different annotators. If the disagreement is high, go back to redefining the task because:

>If you don’t know what a good solution should look like, neither does the neural network

All right, let’s say you have collected a good validation set, and you want to start training your models.

>Have a fixed protocol of comparison

Make an early decision on how to compare the performance of different models -on the same task- with different settings. If you chose to train your model only for 5 epochs and compare the results, then in all your experiments, you should train your models for 5 epochs. If you train your model until your performance plateaus, then this what you should do for every experiment. I personally like overlaying the performance per epoch of every experiment.

>Do NOT fix annotation errors

Sometimes you may find errors in the annotation sets, which is very natural. Make sure that you keep track of them but do not fix them. If you do, you cannot compare your future results with your past benchmarks. If you find major errors that invalidate your previous results, fix the annotations, but make sure you repeat all your past experiments and update your results with them.

>Find the measurement that works for you

There are plenty of measurements, each capture one aspect of your method. Make sure you pick the right measurements. If you are solving a binary classification task in unbiased settings where 99.9% of cases are negative, maybe “AP” is a better measurement for you than “Accuracy.” Also, a mixture of measurements usually brings insights that every one of them individually cannot. For example, if your error is decreasing over the validation set, but the loss value is increasing, then your model is most likely losing calibration and needs more regularization.

>Log-log graphs are easier to interpret, much easier

It is much easier to monitor the performance saturation on the log-log graphs than the linear ones. For this reason, I prefer metrics that decrease with time like “error” to “accuracy.” In the hypothetical scenario below, two models (blue and red) are trained on a binary classification task, and their performance is plotted as a function of training iterations.

It is hard to come up with a conclusive decision from the linear graphs, but the log-log graph shows the blue model continues to learn while the red model is over-fitting.
Spend time on time management

>Format, copy and store your data once

Another great portion of time spent on deep learning is the training time. Especially when trying to find the best hyperparameters. make sure that you:

>Keep track of your work in a way that you don’t need to repeat an experiment

Always log the performance of every experiment with all the hyper-parameters, so you don’t have to repeat any experiment twice.