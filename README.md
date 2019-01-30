<script src="..">のリンク切れや<link href="..">のリンク切れやJSエラーを検出したければたしかにブラウザにGETさせる必要がありますね。

LogEntries les = base.SeleniumBase.driver.manage().logs().get(LogType.BROWSER);

for (LogEntry le : les) {
  String errorMsg = le.getMessage();
  String errorLv = le.getLevel().toString();
  if(errorLv == "SEVERE"){
    writelog.writeLog(prURL, errorMsg);
  }
}
