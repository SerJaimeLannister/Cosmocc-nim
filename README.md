# this is a project to compile nim code to [Actually Portable Executable](https://justine.lol/ape.html)  with the help of cosmocc & [cosmopolitan](https://github.com/jart/cosmopolitan)

## this was created with the help of https://github.com/jart/ & https://github.com/ahgamut/
### this couldn't have been made without their help
### please go sponsor them if possible

the intention of creating this project is that the cosmonim repository https://github.com/rfesi/cosmonim uses cosmopolitan-amalgamation which in the newer versions of cosmopolitan don't exist
Instead this uses cosmocc.

I really suck at writing so this time I have forced myself to write as clearly as possible without much edgecases

# steps to use this
1. Install Latest Version of Cosmocc
-  you could do this by installing it from your package manager (for example , archlinux supports it , but then you would need to look where its located which is not recommended)
-  (preferred) by going to https://cosmo.zip/pub/cosmocc/ and then downloading the latest version

2. Extract the zip file

3. Go to the folder where you extracted and get its path (by doing pwd for example)

4. Run this command and change /path/to/cosmo-folder to actual folder where its located (paste the path from step 3)

On Linux / Mac OS / BSD

```export CC=/path/to/cosmo-folder/bin/cosmocc #change the path to actual folder ```

On Windows (I don't use windows but I searched on stackoverflow and it seems that this command should work though I am not sure)

```[Environment]::SetEnvironmentVariable("CC", "C:\path\to\folder", "User")```


5. Then create a nim file and nim.cfg (install nim if you haven't)

6.  then copy this into your nim.cfg / change your operating system to the one you are using I suppose
```--os:linux
--gc:orc # Not required, but ARC/ORC would obviously work much better for a target like Cosmopolitan
--threads:off # Nim 2 enables threads by default, disable them since I don't think they're needed?
--cc:env
```

7. run nim c file_name.nim which should create a binary in the ape format.
