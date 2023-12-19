import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

public class YourClassName {

    public static Connection connect() throws SQLException {
        String url = "jdbc:mysql://localhost/database";
        String user = "username";
        String password = "password";

        try {
            return DriverManager.getConnection(url, user, password);
        } catch (SQLException e) {
            throw new SQLException("Failed to connect to the database.", e);
        }
    }

    public static void main(String[] args) {
        try (Connection connection = connect()) {
            // Do something with the connection if needed
        } catch (SQLException e) {
            e.printStackTrace(); // Handle the exception appropriately
        }
    }
}
