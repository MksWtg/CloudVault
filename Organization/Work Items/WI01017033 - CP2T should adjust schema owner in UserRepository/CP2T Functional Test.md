
Prerequisites: [[WI01017033 - CP2T should adjust schema owner in UserRepository]], [[What is Copy Production to Test]]

My laptop and the management server are on the same network. I cannot log into the management server. However, I have SSMS admin access to the management server. 

Right now I have a database backup .bak on my machine. I have a special tool called DBBR that does a controlled restoration + some extra stuff. DBBR can only access local files to the server it restores to. But it can connect to any server, my computer or the management server. I want to use DBBR to restore my .bak on the management server. How can I put .bak on the management server so I can run DBBR on my computer, connect to the server, do the restore for the server then vaildate by connecting to this server via SSMS?

Or is it impossible?

![[Pasted image 20260325130124.png]]

**Note**: next time we have to do this (restore a file across multiple machines), rather than using xp shell commands to put the database backup on the machine from a network share, we can simply paste the path to the network share into the tool directly- you can't navigate to this path inside the tool itself but if you provide the path directly the tool will use it.