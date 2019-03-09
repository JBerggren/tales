# The mysterious death note (or how to read a stacktrace)
![Image of mystery](https://jonatanberggren.se/images/deathnote.jpg)
> Something terrible has happened.

The panic could clearly be heard. Something truly awful had happened.

> Filip is DEAD!

> What?! What happened?

> I don't know. There is a message but I can't figure it out

```
Unhandled Exception: System.Net.WebException: The remote name could not be resolved
   at System.Net.FtpWebRequest.GetResponse()
   at System.Net.WebClient.GetWebResponse(WebRequest request)
   at System.Net.WebClient.DownloadBits(WebRequest request, Stream writeStream)
   at System.Net.WebClient.DownloadFile(Uri address, String fileName)
   at System.Net.WebClient.DownloadFile(String address, String fileName)
   at FileImportAndProcessing.FTPRetreiver.RetreiveFile(String ftpServer, String username, String password) in C:\projects\spikes\42Labs\FileImportAndProcessing\FTPRetreiver.cs:line 11
   at FileImportAndProcessing.FileRetreiver.RetreiveFileContent(FileOriginInformation file) in C:\projects\spikes\42Labs\FileImportAndProcessing\FileRetreiver.cs:line 7
   at FileImportAndProcessing.ImportProductCatalogTask.Run() in C:\projects\spikes\42Labs\FileImportAndProcessing\ImportProductionCatalogTask.cs:line 8
   at FileImportAndProcessing.TaskRunner.RunImports() in C:\projects\spikes\42Labs\FileImportAndProcessing\TaskRunner.cs:line 8
   at FileImportAndProcessing.Program.Main(String[] args) in C:\projects\spikes\42Labs\FileImportAndProcessing\Program.cs:line 10
```

Filip of course being “FILe Import and Processing”, a command line program to import data files. Among other things the main product catalog. This was bad.

> I see. I think I know what happened.

> You do?! How? It’s just gibberish. 

> Let me just ask you a few questions to be sure. Has anything in the configuration or source code changed since it last ran successfully?

> No, according to GIT the last change was a month ago and it ran successfully yesterday

> Ok, pretty sure now what it is. But does the server otherwise seem to be functioning? Are there other things running on it that still functions?

> Yes

> Ok, the dns name for the FTP-server where the product catalog is stored has changed

> What? They wouldn’t change that without telling us!

> Really?

> Ok, let me check....The  !#!”#¤”¤%#¤%#¤%! How stupid can they be not telling us? But how did you know?

> Easy, just read the stacktrace. The actual exception: “System.Net.WebException: The remote name could not be resolved” tells us that it cannot look up the remote name, aka do a DNS resolve to get a IP-number from the name of a server. Since you told me that other services on the server are running I ruled out that it was the server having DNS issues.

> Ok, but how did you know that it was the product catalog server?

> Well that was just as easy. Just read the rest of the stack trace
```
at FileImportAndProcessing.FTPRetreiver.RetreiveFile(String ftpServer, String username, String password) in C:\projects\spikes\42Labs\FileImportAndProcessing\FTPRetreiver.cs:line 11
   at FileImportAndProcessing.FileRetreiver.RetreiveFileContent(FileOriginInformation file) in C:\projects\spikes\42Labs\FileImportAndProcessing\FileRetreiver.cs:line 7
   at FileImportAndProcessing.ImportProductCatalogTask.Run() in C:\projects\spikes\42Labs\FileImportAndProcessing\ImportProductionCatalogTask.cs:line 8
```

> The exception is happening in FTPRetreiver which is called from the FileRetreiver which in turn is called from the ImportProductCatalogTask class. Kind of a bit obvious naming there. 

> Ahh, I see. Wow, I didn’t really believe that stacktraces where important. 

> That, young padawan, is why you failed. 
