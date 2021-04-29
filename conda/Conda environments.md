# Conda environments
#til/conda

I use conda environments, but not frequently enough to every remember the commands. Usually, I find myself wondering if I need to create a new environment or do I have one appropriate for my current needs. But how do I list the existing environments?
```
conda info —envs
```
This seems obvious, but I never seem to remember.

Now that I have my list of environments, do I have one that meets my current needs? No? Well, do I add packages to the current environment or do I create a new environment?

To add packages, I just need to execute this command:
```
conda activate ENVNAME
conda install PKGNAME
```

But if I need a new environment, then I need the command:
```
conda create —name ENVNAME
```

Of course, there are more options to all of these commands, but this is a good start.






