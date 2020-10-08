# djangular

## Set up project

Generate public key and add to Github
ssh-keygen
cat ~/.ssh/id_rsa.pub

Init git and push changes
git config --global user.email {mail}
git config --global user.name {name}
git push

Create virtual environment for Python
python3 -m venv .py

Enable and disable virtual python
source ./.py/bin/activate
deactivate

Install Django
pip install django
pip install djangorestframework

Install Sqlite
sudo apt-get install sqlite3

Prepare DB
python manage.py makemigrations
python mangae.py migrate

View DB
open db.sqlite3 

Run web server
python manage.py runserver


## ToDo

Fix open db.sqlite3

Fix scrumboard/cards AttributeError => done

python manage.py shell
>>> from scrumboard.serializers import CardSerializer
>>> serializer = CardSerializer()
>>> print(repr(serializer))
CardSerializer():
    id = IntegerField(label='ID', read_only=True)
    title = CharField(max_length=100)
    description = CharField(allow_blank=True, required=False, style={'base_template': 'textarea.html'})
    story_points = IntegerField(allow_null=True, required=False)
    business_value = IntegerField(allow_null=True, required=False)
    list = PrimaryKeyRelatedField(queryset=List.objects.all())

Request Method:	GET
Request URL:	http://127.0.0.1:8000/scrumboard/cards
Django Version:	3.1.2
Exception Type:	AttributeError
Exception Value:	
Got AttributeError when attempting to get a value for field `title` on serializer `CardSerializer`.
The serializer field might be named incorrectly and not match any attribute or key on the `List` instance.
Original exception text was: 'List' object has no attribute 'title'.

Card Api
GET /scrumboard/cards
HTTP 200 OK
Allow: GET, HEAD, OPTIONS
Content-Type: application/json
Vary: Accept

[
    {
        "id": 1,
        "title": "My first scrum card",
        "description": "List of things to to",
        "story_points": null,
        "business_value": null,
        "list": 1
    },
    {
        "id": 2,
        "title": "My first taxes",
        "description": "Do this before February 1st",
        "story_points": null,
        "business_value": null,
        "list": 1
    }
]

