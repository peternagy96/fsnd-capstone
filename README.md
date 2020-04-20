# Club Musicbox App Backend

This application can be used to store songs and playlists in a database.
Once there are some playlists and songs stored, songs can be added to any number of playlists.

There is role-based access enabled, and the two roles are DJ and Club Manager. Club managers are allowed to do all possible operations.
DJs are limited to viewing the already added songs and playlists, 
and adding/removing songs to specific playlists. 

Users without the aformentioned roles are only allowed to view the
list of playlists available on the server.

## Getting Started

### Installing Dependencies

#### Python 3.7

Follow instructions to install the latest version of python for your platform in the [python docs](https://docs.python.org/3/using/unix.html#getting-and-installing-the-latest-version-of-python)

#### Virtual Enviornment

We recommend working within a virtual environment whenever using Python for projects. This keeps your dependencies for each project separate and organaized. Instructions for setting up a virual enviornment for your platform can be found in the [python docs](https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/)

#### PIP Dependencies

Once you have your virtual environment setup and running, install dependencies by naviging to the `/backend` directory and running:

```bash
pip install -r requirements.txt
```

This will install all of the required packages we selected within the `requirements.txt` file.

##### Key Dependencies

- [Flask](http://flask.pocoo.org/)  is a lightweight backend microservices framework. Flask is required to handle requests and responses.

- [SQLAlchemy](https://www.sqlalchemy.org/) and [Flask-SQLAlchemy](https://flask-sqlalchemy.palletsprojects.com/en/2.x/) are libraries to handle the lightweight sqlite database. Since we want you to focus on auth, we handle the heavy lift for you in `./src/database/models.py`. We recommend skimming this code first so you know how to interface with the Drink model.

- [jose](https://python-jose.readthedocs.io/en/latest/) JavaScript Object Signing and Encryption for JWTs. Useful for encoding, decoding, and verifying JWTS.

## Running the server

From within the `./src` directory first ensure you are working using your created virtual environment.

Each time you open a new terminal session, run:

```bash
export FLASK_APP=api.py;
```

To run the server, execute:

```bash
flask run --reload
```

The `--reload` flag will detect file changes and restart the server automatically.

## Endpoints
```
GET /tracks
POST /tracks
GET /tracks/\<id>
PATCH /tracks/\<id>
DELETE /tracks/\<id>
GET /playlists
POST /playlists
POST /playlists/\<id>
PATCH /playlists/\<id>
DELETE /playlists/\<id>
```


### GET /tracks
```
- Fetches a dictionary of songs
- Request Arguments: None
- Returns: An object where the primary key is their ID and keys
are the song names and artist names
```

### POST /tracks
```
- Adds a song to the database
- Request Arguments: A dictionary with the song and artist names
- Returns: -
```

### GET /tracks/\<id>
```
- Fetches a song and the plalyist IDs it is inhcluded in
- Request Arguments: song ID to be fetcheds
- Returns: An object where the primary key is their ID and keys
are the song names and artist names and the playlists as a list
in which the song appears
```

### PATCH /tracks/\<id>
```
- Adds a song to the database
- Request Arguments: A dictionary with the song and artist names
- Returns: -
```

### DELETE /tracks/\<id>
```
- Adds a song to the database
- Request Arguments: A dictionary with the song and artist names
- Returns: -
```

### GET /playlists
```
- Fetches a dictionary of playlists
- Request Arguments: None
- Returns: An object where the primary key is the playlist IDs and keys
are the playlist names and the number of songs stored on them
```

### POST /playlists
```
- Adds a playlist to the database
- Request Arguments: Dictionary wit hthe name of the playlist as a key
- Returns: -
```

### POST /playlists/\<id>
```
- Adds a song to the playlist with the given ID
- Request Arguments: The ID of the song to be added
- Returns: -
```

### PATCH /playlists/\<id>
```
- Updates a playlist name in the database
- Request Arguments: A dictionary with the new playlist name
- Returns: -
```

### DELETE /playlists/\<id>
```
- Deletes a song from a playlist with the given ID
- Request Arguments: The song ID to be deleted
- Returns: -
```
