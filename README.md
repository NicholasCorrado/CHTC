# f

This repo simulates random actions in all environments included in `gym` (no extra environments like atari).

## Running Locally

```commandline
conda create -n chtc python=3.9
conda activate chtc
git clone git@github.com:NicholasCorrado/CHTC.git
pip install -e CHTC
```
To run:
```commandline
python simulate.py
```

## Running on CHTC

See [here](https://chtc.cs.wisc.edu/uw-research-computing/python-jobs.html) for a thorough overview of how to setup jobs with CHTC.

### 

```commandline
git clone git@github.com:NicholasCorrado/CHTC.git
cd chtc
condor_submit job.sub
```
Output logs (`job.err`, `job.out`, `job.log`) are written to the `results` directory. 
Upon success, `job.out` will contain (modulo randomness):

```commandline
Simulating CartPole-v0...
Average return over 10 episodes: 122.30453232317942 +/- 34.533571653052164

...

Simulating HumanoidStandup-v4...
Average return over 10 episodes: 132.71190201448096 +/- 37.4015262587107

Successfully tested all environments
```
and `job.err` will be empty.

### Getting Dependencies

The dependencies in `packages.tar.gz` were obtained as follows:

```commandline
git clone git@github.com:NicholasCorrado/CHTC.git
cd chtc/packages
condor_submit job_packages.sub
```
Upon completion, a `packages.tar.gz` tarball  will be outputted to the `packages` directory.

`packages.tar.gz`: contains all dependencies. 
See [here](https://chtc.cs.wisc.edu/uw-research-computing/python-jobs.html) 
for an overview on how to get a tarball of your project dependencies.

```commandline
condor_submit job.sub
```
```commandline
conda create -n chtc python=3.9
conda activate chtc
git clone git@github.com:NicholasCorrado/CHTC.git
pip install -e CHTC
```