#### Aggregation refers to calculating values from a group of rows in a model, such as: Total, Average, Maximum, Minimum, Count etc

#### Django provides these through the django.db.models module.
## How to Use:
```python
    from django.db.models import Avg, Max, Min, Sum, Count
    from .models import Book

    # Example: Average rating of all books
    avg = Book.objects.all().aggregate(Avg('rating'))
    avg = Book.objects.all().aggregate(average=Avg('rating'))

    # Example: Total number of books
    total_books = Book.objects.aggregate(total_books=Count('id'))
    total_books = Book.objects.aggregate(Count('id'))

    # Example: Maximum rating
    max_rating = Book.objects.aggregate(Max('rating'))

    # Example: Sum of all ratings
    sum = Book.objects.aggregate(Sum('rating'))
```

#### Each aggregation returns a dictionary, so it is better to give the key a name so it can return a readable key:value:
```python
    print(avg)
    Result = {'rating__avg': 4.5}
    print(total_books)
    Result = {'total_books': 10}
```

#### Ordering is about sorting query results based on one or more fields.
```python
    from .models import Book

    # Order by rating (ascending)
    Book.objects.all().order_by('rating')

    # Order by rating (descending)
    Book.objects.all().order_by('-rating')

    # Order by multiple fields (rating descending, then title ascending)
    Book.objects.all().order_by('-rating', 'title')
```

#### Aggregation and django ORM method .count() can still work with filtering

###### For count()
```python
    Book.objects.filter(rating__gt=4).count() # returns 3
```

##### For aggregation
```python
    Book.objects.aggregate(
        average=Avg('ratings'),
        total_count=Count('id'),
        high_rated_book=Count('id', filter=Q(rating__gt=4))
        )
