# Estimating

Calculate a pool of estimates using the Evidence Based Scheduling technique in Python, and then create a simple visualization using matplotlib:

```python
import random
import matplotlib.pyplot as plt

def generate_ebs_estimates(task_estimates, velocities, n_estimates=3000):
    estimates = []
    for i in range(n_estimates):
        estimate = 0
        for eta in task_estimates:
            estimate += eta * random.choice(velocities)
        estimates.append(estimate)

    return estimates

task_estimates = [...]
velocities = [...]

estimates = generate_ebs_estimates(task_estimates, velocities)

plt.hist(estimates, 30)
plt.show()
```

You can also use Numpy to calculate percentiles on the estimate pool.

## Links

[Evidence Based Scheduling](https://www.joelonsoftware.com/2007/10/26/evidence-based-scheduling/) \#article - by Joel Spolsky. “Over the last year or so at Fog Creek we’ve been developing a system that’s so easy even our grouchiest developers are willing to go along with it. And as far as we can tell, it produces extremely reliable schedules. It’s called Evidence-Based Scheduling, or EBS. You gather evidence, mostly from historical timesheet data, that you feed back into your schedules. What you get is not just one ship date: you get a confidence distribution curve, showing the probability that you will ship on any given date.”

[Evidence Based Scheduling](https://www.fogbugz.com/evidence-based-scheduling.html) \#article - FogBugz explanation. “EBS it’s a statistical algorithm that produces ship date probability distributions. It gather evidence, mostly from historical timesheet data and provides accurate schedules. It produces a probability distribution curve, so that you know for any given date, the probability that your project will be completed by it. EBS is perfect for forgetful team members, and it also takes into account factors like holidays and vacation time. It even consider contributions from those who only occasionally get a chance to work on project stuff too, like busy managers!”

[Evidence-based scheduling](https://en.wikipedia.org/wiki/Evidence-based_scheduling) \#article - on Wikipedia. “Evidence-based scheduling is a software estimation approach created by Joel Spolsky, a commentator on software engineering principles. Evidence-based Scheduling is based on at least two core ideas: including all time spent, and using a Monte Carlo completion date prediction method.”

[Here’s Why All Your Projects Are Always Late — and What to Do About It \(Ep. 323 Rebroadcast\)](http://freakonomics.com/podcast/project-management-rebroadcast/) \#podcast - "Whether it’s a giant infrastructure plan or a humble kitchen renovation, it’ll inevitably take way too long and cost way too much. That’s because you suffer from “the planning fallacy.” \(You also have an “optimism bias” and a bad case of overconfidence.\) But don’t worry: we’ve got the solution."

[Make Better Software: The Training Series - Module 4: Schedules](https://www.youtube.com/watch?v=EUS4ktQJOSY) \#video - "Fog Creek Software invented the most reliable method for shipping software on time and on schedule, like clockwork. It’s called Evidence Based Scheduling, and you’ll learn how to apply it to accurately predict when software projects will be ready."

[Reference class forecasting](https://en.wikipedia.org/wiki/Reference_class_forecasting) \#article - Wikipedia. "**Reference class forecasting** or **comparison class forecasting** is a method of predicting the future by looking at similar past situations and their outcomes.The theories behind reference class forecasting were developed by [Daniel Kahneman](https://en.wikipedia.org/wiki/Daniel_Kahneman) and [Amos Tversky](https://en.wikipedia.org/wiki/Amos_Tversky). The theoretical work helped Kahneman win the [Nobel Prize in Economics](https://en.wikipedia.org/wiki/Nobel_Prize_in_Economics)."

[Software Estimation: Demystifying the Black Art](https://www.amazon.com/Software-Estimation-Demystifying-Developer-Practices/dp/0735605351) \#book

