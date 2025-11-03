# Django Admin Integration for Bookshelf App

## Step 1: Register the Model
Edited `bookshelf/admin.py` to register the Book model:
```python
from django.contrib import admin
from .models import Book
admin.site.register(Book)

# Customize admin interface for book
@admin.register(Book)
class BookAdmin(admin.ModelAdmin):
    list_display = ('title', 'author', 'publication_year')
    list_filter = ('publication_year', 'author')
    search_fields = ('title', 'author')

# Run the server
python manage.py runserver
