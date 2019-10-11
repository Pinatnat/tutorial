# Διαχείριση μέσω Django admin

Για να προσθέσουμε, επεξεργαστούμε και να διαγράψουμε τις δημοσιεύσεις που έχουμε αναρτήσει, θα χρησιμοποιήσουμε την εφαρμογή Django admin.

Ας ανοίξουμε το αρχείο `blog/admin.py` μέσα σε έναν code editor και ας αντικαταστήσουμε τα περιεχόμενα του με τα ακόλουθα:

{% filename %}blog/admin.py{% endfilename %}

```python
from django.contrib import admin
from .models import Post

admin.site.register(Post)
```

Με τον παραπάνω κώδικα, εισάγουμε το μοντέλο Post (δηλαδή τον πίνακα της βάσης δεδομένων με το όνομα Post) όπως ορίστηκε από το προηγούμενο κεφάλαιο. Για να κάνουμε το μοντέλο μας ορατό στην σελίδα διαχείρισης θα πρέπει να το "εγγράψουμε" (να το κάνουμε register) με την συνάρτηση `admin.site.register(Post)`.

Εντάξει λοιπόν, ας ρίξουμε μια ματιά στο Post μοντέλο μας. Θυμηθείτε ότι πρέπει πρώτα να πληκτρολογήσουμε `python manage.py runserver` στην κονσόλα μας ώστε να ξεκινήσει ο development server. Πηγαίνετε στον browser και πληκτρολογήστε http://127.0.0.1:8000/admin/. Θα δείτε μία σελίδα σύνδεσης όπως αυτή:

![Login page](images/login_page2.png)

Για να συνδεθείτε, χρειάζεται να δημιουργήσετε έναν *superuser*, δηλαδή έναν χρήστη ο οποίος θα έχει δικαιώματα σε οτιδήποτε σε αυτή την σελίδα. Πηγαίνετε πίσω στην γραμμή εντολών, πατήστε Ctrl + c για να σταματήσετε τον development server Που ήδη τρέχει, πληκτρολογήστε `python manage.py createsuperuser` και πατήστε enter.

> Θυμηθείτε, για να γράψετε νέες εντολές ενώ ο server εκτελείται, ανοίξτε μια νέα κονσόλα και ενεργοποιήστε το virtualenv. Είδαμε πως να γράφετε νέες εντολές μέσα στο κεφάλαιο **Το πρώτο σας Django project!**, στην ενότητα **Ξεκινώντας τον web server**.

{% filename %}Mac OS X or Linux:{% endfilename %}

    (myvenv) ~/djangogirls$ python manage.py createsuperuser
    

{% filename %}Windows:{% endfilename %}

    (myvenv) C:\Users\Name\djangogirls> python manage.py createsuperuser
    

Όταν σας ζητηθεί, πληκτρολογήστε το όνομα χρήστη σας (πεζά, δίχως κενά), το email σας και ένα password. **Μην ανησυχείτε όταν πληκτρολογείτε τον κωδικό σας και δεν βλέπετε κάτι στην οθόνη. Έτσι πρέπει να είναι.** Πληκτρολογήστε τον και μετά πατήστε `enter` για να συνεχίσετε. Η απόκριση από το τερματικό θα μοιάζει κάπως έτσι (όπου "όνομα χρήστη" και "email" θα είναι τα δικά σας):

    Username: ola
    Email address: ola@example.com
    Password:
    Password (again):
    Superuser created successfully.
    

Αν ο server δεν τρέχει κάντε το τώρα: <0>python manage.py runserver</0>. Μετά, επιστρέψτε στον browser σας. Κάντε login και εισάγετε το όνομα χρήστη και τον κωδικό σας. Θα πρέπει να δείτε, επιτέλους, την κεντρική σελίδα διαχείρισης του Django.

![Django admin](images/django_admin3.png)

Πηγαίνετε στα Posts και πειραματιστείτε με αυτά. Προσθέστε πέντε ή έξι posts. Μην ανησυχείτε για το περιεχόμενο των posts. Είναι μονάχα ορατό σε εσάς, στον υπολογιστή σας. Μπορείτε να κάνετε αντιγραφή-επικόλληση κείμενο από αυτόν εδώ τον οδηγό για να γλυτώσετε χρόνο. :)

Σιγουρευτείτε ότι δύο ή τρία posts (αλλά όχι όλα) έχουν συμπληρώσει το πεδίο "publish date". Θα μας βοηθήσει αυτό αργότερα.

![Django admin](images/edit_post3.png)

If you want to know more about Django admin, you should check Django's documentation: https://docs.djangoproject.com/en/2.2/ref/contrib/admin/

Αυτή είναι μάλλον μια καλή στιγμή να πιείτε μια γουλιά καφέ (ή τσάι) ή κάτι να φάτε για να γεμίσετε ενέργεια. Μόλις δημιουργήσατε το πρώτο σας Django model. Αξίζετε ένα μικρό διάλλειμα!