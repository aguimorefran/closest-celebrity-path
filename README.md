# Closest path to celebrities
This tool will help you find the nearest celebrities following the rules you want.
It is as easy as writing your `Twitter` username, configuring the search `rules` and let the program do the work for you.

## How do I make it work?
1. First, you have to install the requirements from the `requirements.txt` file by running:
> pip install -r requirements.txt

or

> conda create --name <env_name> --file requirements.txt

2. Then, set `me` variable to your **Twitter** username (without @).
3. Let the notebook run ;)

## But how does it work?
This program is based on simple depth-first search and graph theory for representation (or later data mining).

The main contratint (and motivation) are Twitter API rate limits. Please refer to: https://developer.twitter.com/en/docs/twitter-api

This rate limits (and free version of the API) do not allow is to make request for every piece of data we want, so a workaround was made.

As we do not want to loose data on every run of the program, the information had to be persistent, so `sqlite3` is used. For now, the tables are:

1. **Users**: twitter user `id`, `screen_name` (or username), `follower_count`, `friend_count`, `followers`, `friends`, `mutuals` and `verified`.
2. **Paths**: `id`, `path`, `src`, `dst`, `len`, `rules` that were used.
