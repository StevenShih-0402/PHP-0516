<!DOCTYPE html>
<html>
	<head>
		<meta charset = "utf-8"/>
		<title>檢查檔案</title>
	</head>
	
	<body>
		<?php
			$file = "checkdata";
			
			if(file_exists($file. ".php"))				//檢查檔案是否存在
				print("檔案： $file.php 存在<br/>");
			else
				print("檔案： $file.php 不存在<br/>");
			
			if(!copy($file. ".php", $file. ".bak"))		//複製檔案(來源檔案，目的地)，成功或失敗會回傳true 或 false
				print("檔案： $file.php 複製成bak成功<br/>")
			else
				print("檔案： $file.php 複製成bak失敗<br/>")
			
			rename($file. ".bak", "checkdata.txt");			//檔案更名
			print("檔案： $file.bak 更名成checkdata.txt<br/>");
			
			$file = "checkdata.txt";
			
			unlink($file);				//刪除檔案
			print "檔案： $file 已經刪除<br/>";
		?>
	</body>
</html>
