# API for Yatube social network
This is open-source API for the one and only network great devs use - Yatube.

## Important aspects
1. Latest API version is `v1`
2. All API urls start with `api/<api_version>/...`
3. This API implies that you have at least superficial knowledge of what Yatube is and how it works
4. Authentication by JWT-tokens
5. If you run into any problems or simply want to share your experience or ideas, contact us at maks.truxinov@yandex.ru

What it's for:
 + All the functions of Yatube packed in a concise manner for you to use and, hopefully, enjoy

## How to install it on your VM
The following points are roughly as they should be. You should do as you are accustomed to - it's your machine, you know it best

1. Clone it
 - `git clone https://github.com/StriderDunedain/api_final_yatube`
2. Install virtual environment
 - `python -m venv venv`
3. Activate virtual environment
 - `source venv/Scripts/activate` or simply `venv/Scripts/activate`
4. Install necessary requirements 
 - `pip install -r requirements.txt`
5. Change directory
 - `cd yatube_api`
6. Make migrations
 - `python manage.py migrate`
7. Run server
 - `python manage.py runserver`
8. Enjoy making requests to our service :)

## What this current-version API can do:
1. Get (one or all), create, modify and delete posts and comments
2. Get all groups or one specific 
3. Get and create subscriptions
4. Get access and refresh tokens using JWT-tokens and create users using djoser (see "Examples of usage")

## Examples of usage
1. Sending a request to make a post
 - POST-request to `api/v1/posts/` with a required `text` field and two optional fields `image` and `group`
2. Getting all posts (imortant - the resulting JSON object is paginated and therefore does not have all posts in one bundle)
 - GET-request to `api/v1/posts/`
3. Sending a request to make a post
 - POST-request to `api/v1/posts/<post_id>/comments/` with required `post_id` and `text` fields
4. Getting all comments (imortant - the resulting JSON object is paginated and therefore does not have all comments in one bundle)
 - GET-request to `api/v1/posts/<post_id>/comments/` with required `post_id` field
7. Register a new user
 - POST-request to `api/v1/auth/` with required `username` and `password` fields
8. Get access and refresh tokens (for more see official JWT and djoser documentation)
 - POST-request to `api/v1/jwt/create/` and `api/v1/jwt/refresh/` respectively with required `username` and `password` fields

### Afterword
We hope you enjoy our API and Yatube :)
If you see any problems along the way or simply want to share your experience and ideas regarding our API feel free to reach out to us at maks.truxinov@yandex.ru 
