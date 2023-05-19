# Stock API


## Built With
* `Java 17`
* `Maven 4.0.0`
* `H2 Database`
* `Spring Boot 3.0.5`
* `IntelliJ IDEA 2023.1 (Community Edition)`
## Data Flow

### 1. Models:
* It consists of **Stock** entity classe along with data members and member functions
* Used **_@Table_** and **_@Entity_** annotations inside the entity class.
* Used Lombok to reduce boilerplate code for pojo class.By using Lombok annotations like _**@Data,**_ **@_NoArgsConstructor_**, **_@AllArgsConstructor_** getters and setters for those object generate automatically.

### 2. Controllers:
* It consists of  **StockController** classesin which used the annotations like **@RestController** to annotate the class as Controller.
* Used annotation **_@GetMapping_** , **_@PostMapping_** , **_@PutMapping_** , **_@DeleteMapping_** to map the HTTP web requests to the specific handler methods.

<br>

### API Reference:
<br>

>Stock API References
<br>

* Add Stocks:
```*.sh-session
  http://localhost:8080/stock/
```

* Get Stock Based On StockType:
```*.sh-session
 http://localhost:8080/stock/type/{stockType}
```

* Get Stocks Above Price And LowerDate:
```*.sh-session
 http://localhost:8080/stock/abovePrice/price/{price}/lowerData/date/{date}
```

* Get All Stocks Above MarketCap:
```*.sh-session
 http://localhost:8080/stock/cap/{capPercentage}
```
* Update StockType By Id:
```*.sh-session
http://localhost:8080/stock/stock/type/id
```
* Update Stock By Id:
```*.sh-session
http://localhost:8080/stock/stock/{id}
```
* Update Stock MarketCap By Id:
```*.sh-session
http://localhost:8080/stock/marketCap/{marketCap}/id/{id}
```
* Delete Stocks By OwnerCount:
```*.sh-session
http://localhost:8080/stock/ownerCount/{count}
```
<br>



### 3. Services:
* It consists of **StockService** classe in which provide some business functionalities of every handler methods.
* Used _**@Service**_ annotation to indicate that a class belongs to the service layer.
* Used **_@Transactional_** annotation to separate transaction management code from the code for business logic on the update and delete methods.

### 4. Repositories:
* It consists of **StockRepository** interface that extends CrudRepository which is interface for generic inbuilt CRUD operations on a repository for a specific type. Usually represent the database access layer in an application.
* Used **Iterable** to manage the data of entity classes by performing CRUD operations.
* Used _**@Repository**_ annotation is used to indicate that the class provides the mechanism for storage, retrieval, search, update and delete operation on objects.
* Used _**@Modifying**_ annotation wrote named parameters query using @Query annotation to insert, update, or delete an entity.


## Project Summary
* In this project I performed CRUD operation like add,get,delete and update.<br/>
* Used interface JpaRepository for generic CRUD inbuilt operations like save,saveAll,updateById, etc.
* Used our own custom finder methods and wrote operations using custom queries.