# GSoC Final Report

Final report for my project on Rank Metric McEliece Cryptosystem for SageMath during Google Summer of Code 2019.

Background:
----------

Coding theory is a field of study focused on the transmission of information across possibly noisy channels, such that the noise added to the information does not change its meaning. One of the core objects in coding theory are codes, which usually come with error-correcting properties. In simple terms, a code is a subset of a larger space endowed with a metric. There are numerous types of codes (linear, non-linear), over various metrics (Hamming, rank). However, the most usual codes are linear codes over the Hamming metric.

Among open-source implementations of coding theory functionality, the two main representatives are [SageMath](http://doc.sagemath.org/html/en/reference/coding/index.html) and [GAP (Guava Package)](https://www.gap-system.org/Packages/guava.html). Prior to my project, the coding theory module in SageMath supported only linear codes over the Hamming metric. With my addition to the structure of the objects in the coding module, it now supports many different types of codes and also makes it easier to implement new types of codes.

Read more on the [coding theory module of SageMath](http://doc.sagemath.org/html/en/thematic_tutorials/coding_theory.html).

For more details on the background of my project, read my [initial blogpost](https://medium.com/@em.slukova/gsoc-rank-metric-mceliece-cryptosystem-e28cd3701ba5).

Initial Plan:
------------

My initial plan was to implement necessary tools for rank metric McEliece cryptosystems. During GSoC 2016, there was a SageMath project on rank metric codes. The project did not get very far with regards to the rank metric implementation. My main goal was to finish the work that was started three years ago, i.e. finish tickets on [Linear Rank Metric Codes](https://trac.sagemath.org/ticket/21226) and [Gabidulin Codes](https://trac.sagemath.org/ticket/20970). With remaining time, I planned to build upon my work by creating a class for McEliece cryptosystems, encoding and decoding and generating public and private keys.

Actual Project:
--------------

Before I started work on the rank metric implementation, my mentor recommended looking into a smaller scale ticket on [Goppa Codes](https://trac.sagemath.org/ticket/25977). This gave me a chance to learn about the SageMath development process as well as the coding module, before I made any changes to it.

While studying the current state of the rank metric implementation, it soon became clear to me that having input from someone who worked on the project in 2016 would be priceless. I contacted the mentor from the original project, who offered his help.

After a discussion with him and my mentor we decided that the best way to proceed would be to create an abstract code class in SageMath, [Abstract Code](https://trac.sagemath.org/ticket/28073). After I finished work on that I finally created an initial version of [Rank Metric](https://trac.sagemath.org/ticket/21226). However, a lot of the code overlapped with another linear code class in the coding module. Hence we decided to create yet another level of abstraction, [Abstract Linear Code No Metric](https://trac.sagemath.org/ticket/28350). Not only did this save a lot of code repetition, it also meant that future implementation of linear codes over new metrics will be much easier.

With both [Abstract Code](https://trac.sagemath.org/ticket/28073) and [Abstract Linear Code No Metric](https://trac.sagemath.org/ticket/28350) finished, I edited my work on [Rank Metric](https://trac.sagemath.org/ticket/21226) accordingly. The final step in the project was to focus on [Gabidulin Codes](https://trac.sagemath.org/ticket/20970), a class of linear codes over the rank metric. For this class, some work was already done in 2016. I finished the rest and also rewrote the code to reflect the current state of the coding module.

SageMath offers 'thematic tutorials' to users, which are in-depth documentation files explaining certain topics. There are a few of these dedicated to the coding module. Since I made numerous impactful changes to the module, these tutorials were no longer current. I changed these accordingly and also added some new content, as per [Thematic Tutorials](https://trac.sagemath.org/ticket/28209).

Finally, I created a rough working version for the rank metric [McEliece Cryptosystem](https://trac.sagemath.org/ticket/21352).

List of tickets I worked on:
---------------------------
- [x] [Goppa Codes](https://trac.sagemath.org/ticket/25977)
- [x] [Abstract Code](https://trac.sagemath.org/ticket/28073)
- [x] [Abstract Linear Code No Metric](https://trac.sagemath.org/ticket/28350)
- [x] [Linear Rank Metric Codes](https://trac.sagemath.org/ticket/21226)
- [x] [Gabidulin Codes](https://trac.sagemath.org/ticket/20970)
- [x] [Thematic Tutorials](https://trac.sagemath.org/ticket/28209)
- [x] [McEliece Cryptosystem](https://trac.sagemath.org/ticket/21352)

Blog posts:
----------
During the whole project, I wrote about my work on Medium. Here is a list of links to my blogposts:

- [Project Background](https://medium.com/@em.slukova/gsoc-rank-metric-mceliece-cryptosystem-e28cd3701ba5)
- [Community Bonding](https://medium.com/@em.slukova/community-bonding-and-first-week-57a3d6fb19ad)
- [First Coding Period](https://medium.com/@em.slukova/gsoc-week-two-and-three-93364102338c)
- [Secoding Coding Period](https://medium.com/@em.slukova/gsoc-second-coding-period-eb3ebb179000)
- [Final Coding Period](https://medium.com/@em.slukova/gsoc-final-coding-period-22b671ddcae8)
