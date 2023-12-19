System.out.println("Welcome to Servlet");

Connection con = null;

try {
    Class.forName("com.mysql.jdbc.Driver");
    con = DriverManager.getConnection("jdbc:mysql://localhost:3306/test", "root", "Omsai");

    if (con != null) {
        System.out.println("Connection is established");
    } else {
        System.out.println("Error in connection");
    }
} catch (Exception e) {
    System.out.println(e);
} finally {
    try {
        if (con != null) {
            con.close();
        }
    } catch (SQLException se) {
        System.out.println(se);
    }
}
