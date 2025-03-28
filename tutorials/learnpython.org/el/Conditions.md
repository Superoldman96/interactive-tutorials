Python χρησιμοποιεί λογική boolean για να αξιολογήσει συνθήκες. Οι boolean τιμές True και False επιστρέφονται όταν μια έκφραση συγκρίνεται ή αξιολογείται. Για παράδειγμα:

x = 2
print(x == 2) # εκτυπώνει True
print(x == 3) # εκτυπώνει False
print(x < 3) # εκτυπώνει True

Σημειώστε ότι η ανάθεση μεταβλητής γίνεται χρησιμοποιώντας έναν απλό ίσο χειριστή "=", ενώ η σύγκριση μεταξύ δύο μεταβλητών γίνεται χρησιμοποιώντας τον διπλό ίσο χειριστή "==". Ο «όχι ίσος» χειριστής σημειώνεται ως "!=".

### Boolean operators

Οι boolean χειριστές "and" και "or" επιτρέπουν την κατασκευή σύνθετων boolean εκφράσεων, για παράδειγμα:

    name = "John"
    age = 23
    if name == "John" and age == 23:
        print("Το όνομά σου είναι John, και είσαι επίσης 23 χρονών.")

    if name == "John" or name == "Rick":
        print("Το όνομά σου είναι είτε John είτε Rick.")

### Ο χειριστής "in"

Ο χειριστής "in" μπορεί να χρησιμοποιηθεί για να ελεγχθεί αν ένα συγκεκριμένο αντικείμενο υπάρχει μέσα σε ένα επαναλαμβανόμενο αντικείμενο κοντέινερ, όπως μια λίστα:

    name = "John"
    if name in ["John", "Rick"]:
        print("Το όνομά σου είναι είτε John είτε Rick.")

Η Python χρησιμοποιεί εσοχή για να ορίσει μπλοκ κώδικα, αντί για αγκύλες. Η τυπική εσοχή της Python είναι 4 κενά, αν και οι καρτέλες και οποιοδήποτε άλλο μέγεθος κενών θα λειτουργήσει, εφόσον είναι συνεπές. Σημειώστε ότι τα μπλοκ κώδικα δεν χρειάζονται κάποια τερματική σήμανση.

Εδώ είναι ένα παράδειγμα για τη χρήση της δήλωσης "if" της Python χρησιμοποιώντας μπλοκ κώδικα:

    statement = False
    another_statement = True
    if statement is True:
        # κάντε κάτι
        pass
    elif another_statement is True: # αλλιώς αν
        # κάντε κάτι άλλο
        pass
    else:
        # κάντε κάτι άλλο
        pass

Για παράδειγμα:

    x = 2
    if x == 2:
        print("x ίσον δύο!")
    else:
        print("x δεν είναι ίσο με δύο.")

Μια δήλωση αξιολογείται ως αληθής αν κάποιο από τα παρακάτω είναι σωστό:
1. Η boolean μεταβλητή "True" δίνεται ή υπολογίζεται χρησιμοποιώντας μια έκφραση, όπως ένας αριθμητικός συγκριτικός.
2. Περνάει ένα αντικείμενο το οποίο δεν θεωρείται "κενό".

Εδώ είναι μερικά παραδείγματα για αντικείμενα που θεωρούνται κενά:
1. Ένα κενό string: ""
2. Μια κενή λίστα: []
3. Ο αριθμός μηδέν: 0
4. Η ψευδής boolean μεταβλητή: False

### Ο 'is' χειριστής

Σε αντίθεση με τον διπλό ίσο χειριστή "==", ο χειριστής "is" δεν ταιριάζει με τις τιμές των μεταβλητών, αλλά με τις ίδιες τις παρουσίες. Για παράδειγμα:

    x = [1,2,3]
    y = [1,2,3]
    print(x == y) # εκτυπώνει True
    print(x is y) # εκτυπώνει False

### Ο χειριστής "not"

Η χρήση του "not" πριν από μια boolean έκφραση την αναιρεί:

    print(not False) # εκτυπώνει True
    print((not False) == (False)) # εκτυπώνει False

Άσκηση
--------

Αλλάξτε τις μεταβλητές στην πρώτη ενότητα, έτσι ώστε κάθε δήλωση if να επιλύεται ως True.