```java
import java.sql.Connection;
import java.sql.DriverManager;

public class DatabaseUtil {

	public static  Connection getConnection() {
		
		try {
			String dbURL = "jdbc:mysql://localhost:3306/DB?useUnicode=true&characterEncoding=utf8";
			String dbId = "root";
			String dbPw = "1234";
			Class.forName("org.mariadb.jdbc.Driver");
			return DriverManager.getConnection(dbURL,dbId,dbPw);
		} catch (Exception e) {
			e.printStackTrace();
		}
		return null;
	}

}
```
