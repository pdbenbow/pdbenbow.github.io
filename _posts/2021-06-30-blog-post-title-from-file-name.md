## Test blog post

Due to a plugin called `jekyll-titles-from-headings` which is supported by GitHub Pages by default. The above header (in the markdown file) will be automatically used as the pages title.

If the file does not start with a header, then the post title will be derived from the filename.

This is a sample blog post. You can talk about all sorts of fun things here.

---

### This is a header

#### Some T-SQL Code

```tsql
declare @outstatus nvarchar(max)
	, @outresponse nvarchar(max)
	, @postdata nvarchar(max)

set @postdata = '{"text":"This is another message from the production EDW (bi01) posted directly to Slack using a query in SQL Server so I can verify the new name of the webhook and the new icon."}' 

exec edw.sp_API_Request 'post'
	, ''
	, @postdata
	, 'https://hooks.slack.com/services/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'
	, @outstatus output
	, @outresponse output 

select @outstatus as [response status]
	, @outresponse as [response text]
```

#### Some PowerShell Code

```powershell
Write-Host "This is a powershell Code block";

# There are many other languages you can use, but the style has to be loaded first

ForEach ($thing in $things) {
    Write-Output "It highlights it using the GitHub style"
}
```
