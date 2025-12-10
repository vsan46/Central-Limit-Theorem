# **What is the Central Limit Theorem (CLT)?**

If you are getting into data science or statistics, the CLT is a cornerstone concept.

In simple terms, the Central Limit Theorem states that if you take sufficiently large random samples from any population (even a really weird, non-normal one) and calculate the averages of those samples, the distribution of those sample averages will eventually form a normal distribution (a bell curve).

Furthermore, the center (the mean) of that new bell curve will be extremely close to the actual mean of the original population.

**Why is this amazing?** It means that in the real world, where data is rarely perfectly normally distributed, we can still use powerful statistical tools that assume a normal distribution, as long as we are dealing with averages of samples rather than individual data points.

# **How My Code Demonstrates This**
I built this simulation to visually prove the definition above. Here is the breakdown of my approach:

## **1. The "Non-Normal" Starting Point**

To prove the CLT works, I couldn't start with a normal distribution. I needed something flat. I created a "parent population" of 100,000 data points that simulates rolling a 6-sided die.

If you look at the top chart in the output visualization, you'll see it's a (mostly) flat topped histogram. Rolling a '1' is just as likely as rolling a '6'. This is definitely not a bell curve.

## **2. The Sampling Loop**

This is where the magic happens (specifically in the generate_sample_means function).

1. I take a scoop of data from the parent population (a sample). Let's say the sample size is $n=5$.
2. I calculate the average of those 5 numbers.
3. I record that average.
4. I repeat this process 1,000 times.

I now have a list of 1,000 averages.

## **3. The Visualization Progression**

The code repeats the sampling loop for different sizes of scooping: $n=2, 5, 30,$ and $100$.

The bottom row of charts in the output plots the histogram of those 1,000 averages for each size.

- **At n=2 (bottom left)**: The distribution of averages looks jagged. It's trying to form a triangle, but it's certainly not a smooth bell curve yet.
- **At n=5 & n=30**: You can see the shape tighten up. The tails get thinner, and the center gets taller. It's looking very "bell-like."
- **At n=100 (bottom right)**: We see a beautiful, tight normal distribution.

Notice the red dashed line in all plots. That is the "true mean" of the original die-rolling population (roughly 3.5). Notice how even though the original data was flat, the averages of the samples centered themselves almost perfectly around that true mean.
