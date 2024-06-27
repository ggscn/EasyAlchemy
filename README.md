# EasyAlchemy
Opinionated model mixin for data warehousing and running ETL jobs with SQLAlchemy

Add it as a parent to your models like so to get access to this library's features
```
Base = declarative_base()

class MyTableModel(EasyAlchemy, Base):
    __tablename__ = 'my_table'
```

Once added, you can do the following operations

```
table = MyTableModel()
table.create() #create the table
table.drop() #drop the table
table.append([{'column':'value'}]) #append a list of dicts to the table
table.query('select * from my_table', to_df=True) #query table and read result into pandas DataFrame
table.all() #get all rows from the table
```
