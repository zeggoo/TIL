# 구글시트에서 jdbc연결을 통한 테이블 읽어오기


```javascript
/**
 * Replace the variables in this block with real values.
 * You can find the "Instance connection name" in the Google Cloud
 * Platform Console, on the instance Overview page.
 */
var connectionName = 'Instance_connection_name';
var user = 'user_name';
var userPwd = 'user_password';
var db = 'database_name';

var dbUrl = 'jdbc:google:mysql://' + connectionName + '/' + db;

/**
 * Read up to 1000 rows of data from the table and log them.
 */
function readFromTable() {
  var conn = Jdbc.getCloudSqlConnection(dbUrl, user, userPwd);

  var start = new Date();
  var stmt = conn.createStatement();
  stmt.setMaxRows(1000);
  var results = stmt.executeQuery('SELECT * FROM entries');
  var numCols = results.getMetaData().getColumnCount();

  while (results.next()) {
    var rowString = '';
    for (var col = 0; col < numCols; col++) {
      rowString += results.getString(col + 1) + '\t';
    }
    Logger.log(rowString);
  }

  results.close();
  stmt.close();

  var end = new Date();
  Logger.log('Time elapsed: %sms', end - start);
}
```