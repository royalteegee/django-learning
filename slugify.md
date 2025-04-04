## Slug is a URL-friendly, human-readable identifier used to represent a resource. It is typically a lowercase, hyphen-separated string derived from a title or name. Slugs improve readability, SEO (Search Engine Optimization), and usability.

### How to import
```python
   from django.utils.text import slugify 
```
###### slugify converts strings like this "Nike Boot Lace" to "nike-boot-lace"
###### A slug column is created in the models.py file and the auto save method is overriden by super() save method

### Usage
```python
    class Book(models.Model):
        title = models.CharField(max_length=200)
        slug = models.SlugField(default="", null=False)

    def save(self, *args, **kwargs):
        self.slug = slugify(self.title)
        super().save(*args, **kwargs)
```
