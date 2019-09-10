# creatfile-with-Tsql

--premession
Use Master
GO

EXEC master.dbo.sp_configure 'show advanced options', 1
RECONFIGURE WITH OVERRIDE
GO

EXEC master.dbo.sp_configure 'xp_cmdshell', 1
RECONFIGURE WITH OVERRIDE
GO
-- creat file with location 



DECLARE @Text AS VARCHAR(100)
DECLARE @Cmd AS VARCHAR(100)
SET @Text = 'Hello world '
SET @Cmd ='echo ' +  @Text + ' > E:\AppTextFile.txt'
EXECUTE Master.dbo.xp_CmdShell  @Cmd
