# hibernate-mysql-simple-example
A simple Hibernate MySQL example

Is a ORM framework that maps the object to the relational entities in database. It is Light weight, fast performance, database independent query, automatic table creation, simplifies complex join

Elements of Hibernate 

SESSION FACTORY- heavy weight, only one per application will be created, delivers the session object to the hibernate application, second level cache, thread safe 
Create Session Factory using the below factory beans 
LocalSessionFactoryBean – Hibernate 4, use this from > 3.6 version 
AnnotationSessionFactoryBean – Hibernate 3, this has been merged with the configuration and deprecated. Both does the same job  

SESSION- is lightweight, holds the query object, not thread safe, interface between the application and database, factory of query, transaction and criteria, first lavel cache 

CONFIGURATION FILE- acts as a startup for hibernate, and configure the hibernate and the session object 

CONNECTION PROVIDER - provides the factory for JDBC connections 

TRANSACTION- abstracts the code from JDBC transaction etc. 

TRANSACTION FACTORY - optional 

Query and Criteria - allows to perform queries and control the flow of query execution

Hibernate can use both xml and annotations for persisting object with database 
@Entity - marks class as entity 
Entity class in hibernate requires no arg constructor because Hibernate use reflection to create instance of entity class and it mandates no arg constructor in Entity class 

@Table - marks the table name for which the class should be persisted, if not used hibernate will use the class name as default 
@Table(name = "Project") 

@Transient - will not persist this object 
Private static String name - using static, this will not be presisted also 

@Temporal(TemporalType.Data or Time) - by default Date datatype will save both date and time, using this  
You can save only date or time 

@Lob - tells hibernate to select either Clob (private byte[] name) or Blob (if private String name) in case of large data 

@Column - marks the column of the property in entity, if not specified, property name will be default 

@Id - marks the identifier for the entity… mostly placed on the first element of the entity which will be your primary key 

@GeneratedValue - allows app to generate a sequence.. Auto, identity (database assigns next value), sequence (DB sequence), table () 

@GeneratedValue.AUTO - hibernate decides 

@GeneratedValue.IDENTITY - uses auto-incremented database column (identity Column) to gen id, not good performance  

@GeneratedValue.SEQUENCE - good performance, uses db sequence 

@GeneratedValue.TABLE - stimulates id by storing the current value in table and updating, does pessimistic lock v bad performance 
 
@Embeddable – placed on the class of the embedded class (Address) 

@Embedded – placed on the primary class where Address is declared 
Using embedded objects will not create Address as a new table, but rather it will add all the fields in Address class as new columns in the Student table 
