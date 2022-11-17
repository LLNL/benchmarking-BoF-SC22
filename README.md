# benchmarking-BoF-SC22

## Abstract

HPC centers around the world use benchmarks to evaluate their machines and to engage with vendors during procurement.  The goal of this BoF is twofold. First, a series of short presentations will gather information on the state of the art methodologies for creating and validating the benchmarking sets. Second, an open discussion will  gather community feedback on pitfalls of the current methodologies and how these methodologies should evolve to accommodate the growing diversity of the computational workloads and HPC architectures.  The intended audience is HPC application developers and users, teams benchmarking HPC data centers, HPC vendors, and performance researchers.

## Panel

1.  Moderator: [Olga Pearce](https://people.llnl.gov/pearce8), LLNL, USA
2.  [Brian Austin](https://www.nersc.gov/about/nersc-staff/advanced-technologies-group/brian-austin), NERSC, USA
3.  [Jens Domke](https://domke.gitlab.io), RIKEN, Japan
4.  [Todd Gamblin](https://people.llnl.gov/tgamblin), LLNL, USA
5.  [Josef Weidendorfer](https://www.ce.cit.tum.de/en/caps/staff/josef-weidendorfer), TUM, Germany
6.  [Veronica Vergara](https://www.ornl.gov/staff-profile/veronica-g-melesse-vergara), ORNL, USA


## Please fill out our [SURVEY](https://docs.google.com/forms/d/e/1FAIpQLSearrW0ryZeGPwP4OM5hrv8WgjK86K9WN5jwDXG0BheGGTe7Q/viewform)


## Topics for discussion

### Benchmarking uses

- Hardware evaluation
- Procurement bids (e.g., CORAL2)
- Tracking progress
- Acceptance testing
 

### Challenges

- Many tedious manual tasks
- Build porting/portability across architectures
- Run script porting/portability across architectures
- Need to be run frequently (continuous task?)

###  Benchmark suite components

1.  Software
2.  Building
3.  Running
4.  Run specification for different machines and scales
5.  Output specification
6.  Performance evaluation
7.  CI and contiguous testing



## Notes from the meeting on 11/15/2022

### Olga
- Use them to evaluate hardware, acceptance, etc.
- El Capitán is coming in 2023
- Use internal harness to run tests (functionality, performance, stability)
- Benchmarks have been written and haven’t changed since 2018
- Lulesh has been retired because LLNL no longer uses those algorithms
- Can we do a little better with our benchmarking efforts?
 
### Jens
- Brief overview of the procurement for Fugaku
- Science areas that they wanted to advance with Fugaku
- Where do we use benchmarks?
- Different things to analyze benchmarks
- Hope is that we get help from the community to continue developing
 
### Brian
- NERSC Perlmutter supercomputer
- CPU & GPU partitions (separate)
- 600 different codes ran on Perlmutter
- For procurement, we choose application benchmarks
- NERSC-10 procurement will be released next summer
- Relevant and challenge problems with a 10-year outlook
- Perlmutter represents the next stage of the benchmark system
- Check that the system is healthy
- Defining the run rules, which changes to the benchmark a vendor may be allowed to make during the procurement process
 
### Josef
- Octoberfest 😊
- Difficult to enforce how much time they can spend on optimizations
- Output of the tests are custom results

Challenges:
- keeping benchmark suites up to date
- still a lot of manual work to do
- testbed software stacks are not mature enough
- reproducibility

### Veronica
- Vendor diagnostics, component-specific tests
- Functionality tests
- Performance tests: Running tests on a quiet system is important
- Stability
- [OLCF harness](https://github.com/olcf/olcf-test-harness)

### Todd
- Historically, ran benchmarking the same way Verónica described
- CORAL-2 procurement benchmarks
- It is a giant pain to send tarballs around and it is hard to keep the benchmarks up to date
- Use it for testing our own Linux distribution
- Really common activity – I don’t see why we couldn’t crowd-source
- Building is one of those things that is fairly manual – spack helps with that
- Big community that continues to grow over time
- The cloud is leveraged for CI
- Right now, we use gitlab for CI to ensure a package can still build
- If you can get engagement, I think you can crowd-source
- ReFrame is getting some uptake
- ReFrame you can plug easy-build or spack easily

Gaps:
- Repository of recipes is hard
- Benchmarks don’t have as broader reach as they could
- Publicly shaming people is very effective
- Incentivizes vendors to make improvements
 
### Q&A
- Not a lot there on output or interpretation
- There seems to be a lot of confusion – who understands what benchmarks to what degree
- What/who sets the “pass” criteria?
- Parametrizing can be painful
- Correct answers, performance checks
- Output standardization is very difficult, we’ve seen everything from “OK” to 5GB of output and everything in between
- Smoke test and then get the best performance
- Two ways of thinking about it
- But what is good enough?
- Helps average John/Jane Doe user
- Understanding what the performance was even on the cloud to see if you see a difference
- Perfkit at Google
- Now that I have a result, how do we compare to your results?
- What is our collaboration forum look like?
- Get the community to collaborate, try tools, not wait on consensus
- Reproducible performance:
- How would we containerize a benchmark so people can easily pull the container from the registry?
- Containers won’t give you reproducible performance
- A huge part of benchmarking is to show that a benchmark can hit the best performance after optimization
- If you are running the flags for one site may be different than the other
- Buy-in from library developers may help to broaden who provides the tests
- Some library developers do provide tests already and would be willing to collaborate
- Benchmark suites should be built by anyone that wants to build one
- Maybe don’t think about them as benchmark tools
- If you provide added value to scientists, they may be more willing to contribute
- Having ways to demonstrate the user how to improve their applications to create a feedback loop
- Before you know it, the full workflow will become the next step, but there is still a case for a more specialized tool
- Capturing the environment and the state of the machine:
- Is there a fingerprint per machine?
- Best effort: whatever you can collect
