## Blog One

![Image](https://themaverick.github.io/seniordesign/gifs/neowhat.gif)

### What? Surprise! It's 9:00pm, and can you write this for me? 
Just the other day I was asked by someone in the cybersec industry for some PowerShell advice to locate a file on Windows using only native langauges. He was curious as to how I could do this in a one liner, or even better, a PowerShell script. His issue was locating a file given a file hash of a video he needs to edit without knowing the file name. I tried writing it in under 10 minutes, and it was a great success! Here is what I did. Another issue they had faced was that the machine was single core, which as we all know, 1 core is never better than 2 cores. 

### Starting Features
```markdown
1. Obtain listing of all objects in the local disk where the dcript is run
2. Hash each object and obtain full file path, suppress other files that do not match 
3. Immediately check the hash of the object and compare it with the sought after hash
4. Return file location, hash, and name
```

## Obtain input of hash

![Image](https://themaverick.github.io/seniordesign/media/b1.png)

The needle in the haystack (all the hard drive files we are searching for) is our desired hash. To find this hash we store it into a variable so this way the system can know what to look for in memory.  

## The one liner

The glory of the one liner is that the code is condensed into one line and does not have multiple lines while still completing the job of the script. It is mostly to show off a condensed script. PowerShell one liners have been a thing for quite some time now in industry!

Here is what I wrote:

```
Get-ChildItem -Path C: -recurse | Group-Object Length | Select-Object -ExpandProperty group | ForEach-Object -Parallel  {get-filehash -literalpath $_.fullname} | Where-Object { $_.Hash -eq $needle } -ErrorAction SilentlyContinue
```

Get-ChildItem will obtain a directory listing of the C: drive, which can be converted to a variable to obtain a listing of a drive letter supplied by the user. By we begin to group objects by their length and choosing an object to final their file name which supplies us with their literal paths (full directory path) to a given file. We use the ForEach-Object running in Parallel processing for faster hashing and overrall consuming less time than tpyical without ![parallel processing](https://devblogs.microsoft.com/powershell/powershell-foreach-object-parallel-feature/). Get-FileHash will obtain a hash of each file in the default SHA-256 algorithm. Finally, we will examine each object for our desired needle (the inputted hash by the user). At the end of the script, upon error, we suppress these since there can be access issues to more sensitive system files. 

I believe he was quite happy with the result and was able to locate the file. Fun times!

Download link to script: ![File-Identification.ps1 ](https://themaverick.github.io/seniordesign/scripts/ps1/File-Identification.ps1)