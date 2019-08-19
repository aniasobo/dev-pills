# Database design with CRC cards

**CRC - Class Responsibility Collaborator cards**  

_Class_  

| Responsibilities | Collaborators | 
| --- | --- | 
| action | agent |

---

* one-to-many relationship should exist on the many 
* many-to-many - joined table
* each table should be associated with a class
* joined table doesn't require an id
* joined table is associated with a class - querying the table creates instances of it (add `RETURNING` to the query and a new instance of the class as the implicit return from the method)
* use class methods (`self.`) to query the db associated with a class (not instance methods!)
* never put lists in a table cell - if this is required, it means you need to redesign the table into more than one table

[This resource](https://guides.rubyonrails.org/association_basics.html#the-types-of-associations) has good info on associations between tables