**Advanced Lab:  Domain Driven Design**

Domain Driven Design is a methodology, as Scrum is a methodology, used to decouple complex code into manageable blocks of code that is easily communicated with the business.


The main component of a domain driven design involves creating isolated sections of code called a **Bounded Context**.  The bounded context is an isolated section of code that corresponds to a single business function.  In DDD, tasks that the business unit will perform are considered more important than model schemas.  It is the tasks (or business logic) and not the database that hold the project together.  DDD shifts responsibility to the middleware rather than the backend.


In this lab we will be taking legacy code and subdividing it into bounded contexts using closures.

1.  write some legacy code

```
public Class Order
{
    int ID;
    double price;
    string customer;

}

interface ISalesRepository 
{
    int create (Order o);
    Order read (int id);
    void update (Order o);
    void delete (Order o);
}

public class SalesModel
{
    private double price;
    private ISalesRepository sale;
    
    public int MakeSale(int price, string customer)
    {
        Order myorder = new Order(price, customer);
        return sale.create(myorder);
    }
    public double GetRevenue(int id)
    {
        Order myorder = sale.read(id);
        return myorder.price;

    }
}

```
2.  Add new functionality to the legacy code

The marketing department wants to add a SKU to each order without refactoring the existing code.  What are the business tasks to be handled?

* make a new order
*  get revenue from the order
*  make a new order with sku
* add sku to existing orders

3.  Create a function that uses the existing model

```
Func<double, string, int> legacyModelCreate = (price, customer) =>
{
    SalesModel s = new SalesModel();
    return s.MakeSale(price, customer);
}

```
4.  Create a function that writes a SKU

```
Func<string, int> SKUCreate = (sku, id) =>
{
    //insert sku into orders table with id
}

```

5.  Compose the functions into a closure

```
Func<double, string, int, int> newModelCreate = (price, customer, sku) =>
{
    int id = legacyModelCreate(price, customer);
    return SKUCreate(sku, id);
}

```
This satisfies the make a new order with sku task

6.  On your own, use closures to update existing orders with a sku

