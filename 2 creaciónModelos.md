# Modelos

### Estos modelos se pueden crear como tablas de base de datos con los comandos de migraciones.

### Ejemplo:

# models.py
### Django crea automáticamente el campo de identificación para cada modelo, como se muestra a continuación

    from django.db import models`

    class Customer(models.Model)`
    
    name = models.Charfield('Customer', max_length=120)`
    age = models.IntegerField()
    note = models.TextField(blank=True, null = True)
    email = models.EmailField(max_length=255, blank=True, null=True)
    credit = models.FloatField(blank=True)
    is_active = models.BooleanField(default=True)
    created_at = models.DateTimeField(auto_now_add=True)
    updated_at = models.DateTimeField(auto_now=True)

    # Select Field (return value, display value)
    TYPE_CHOICES = (
        ('Customer', 'Customer'),
        ('Supplier', 'Supplier'),
        ('Student', 'Student'),
    )

    type = models.CharField(choices=TYPE_CHOICES)


# Representación del modelo

    class Customer(models.Model):
    name = models.Charfield('Customer', max_length=120)
    age = models.IntegerField()

    def __str__(self): 
        return self.name

# Relaciones entre modelos

***One-to-Many:*** (use comillas dobles si la entidad aún no está declarada) ejemplo. "Supplier"
    
    supplier = models.ForeignKey(Supplier, blank=True, null=True, on_delete=models.CASCADE)

***on_delete*** se puede configurar en modelos. 

    CASCADE, models.ST_DEFAULT or models.SET_NULL

***Many-to-Many:*** 
    
    tags = models.ManyToManyField(Tag, blank=True)

***One to One***
    
    User = models.OneToOneField(User, on_delete=models.CASCADE)

# Método de guardado de sobrescritura
    def save(self, (*args, **kwargs):
        if not self.slug:
            self.slug = slugify(self.title)

        super().save(*args, **kwargs)
