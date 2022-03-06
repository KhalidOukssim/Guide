# JDBC

## 01 - JDBC's  Steps

00-import packages and driver

01-Connexion to SGBD

02-Create SQL Request

03-Execute the request

04-data returned processing 

05-close Connexion

```java

Class.forName("driverName");
Connection con=DriverManger.getConnextion(url,user,pw)
//1.la plupart des methodes levent java.sql.SQLException
//2.CollableStatement:encaopsule procédure SQL stockées en SGBD
PreparedStatement stm=con.prepareStatement(str)
ResultSet result= stm.executeQuery(requete)//select
ResultSet result= stm.executeUpdate(requete)//other requests
 while(result.next()){
     nom=result.getType(number of column);
 }
resultset or statement or connection close()
 
```

## 02 - Exceptions JDBC

```java
catch(SQLException e){
    System.err.println(e.getMessage());  
}//e.getErrorCode()
```

## 03 - ResultSet

1. next(),previous(),first(),last()
2. updateInt(),getDouble

## 04 - Transaction

```java
connect.setAutoCommit(false) //definir une composé de +ieurs request SQL
con.commit()//:valider transaction
con.rollback()//annuler transaction
```

## 05 - Batch

```java
st.addBatch("INSERT...");
int[] nb=st.executeBatch();

```

