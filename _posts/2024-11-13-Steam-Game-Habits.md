---
layout: post
title:  "Too Many Games, Too Little Time"
description: Exploring a dataset of Steam games from user Gimotac
image: /assets/img/Gimotac_Account.png
---
<p class="intro"><span class="dropcap">H</span>ow we spend our free time is important. Depending one what we do, it can bring us closer to or farther from our loved ones, increase or decrease our stress, or many other things. For me, I occasionally enjoy relaxing by playing video games on my own and with my wife. Steam is the biggest video game distributor on PC. If you play any PC game besides Minecraft, Fortnite, or Microsoft Solitaire, you likely have Steam installed and at least a few games in your Steam Library. For me, I have over 300 games on Steam and love playing on my Steam Deck that my wife got me for Christmas last year. As we explore my Steam library showing how I spend some of my time, I hope you find this interesting and can reflect on how you spend your free time.</p>

# Why Do I Care?
Since discovering this API, I wanted to explore my Steam library data more closely than just what Steam shows on my profile page. Some specific questions include what proportion of games have I actually played out of my entire library, what does the distribution of gametime look like, what games have I played the most (while excluding Terraria, since I used to share this account with my brother and he racked up over 450 hours on that game), and how much of recent games I have played.

# Ethics
In much of data science, we would use data that is provided to us by an employer or contractor. When using data from other places, there may be rules and policies to which we agree so we can access and use said data. In all cases, we must be careful in how we handle the data to follow those rules and to respect the privacy and security of ourselves and others. With this data specifically, I signed up with Steam's API and received an API key. Part of Steam's policy is that I can only access the data of a given account with permission from the account owner. Naturally, since I am the account owner, I have my own permission to use it. Please be mindful when collecting and using data in your Data Science journey.
*I should note here that this is personal data and while you are welcome to view the information found in this blog post and related links, I do not give permission to view my Steam account data through the Steam API*

# How Would You Get This Data?
To get this data, as previously mentioned, I signed up for Steam API access and received a Steam API Key. You can do this as well by filling out this form referenced on the [Steam Web API Documentation](https://steamcommunity.com/dev) page, which also has references for accessing other data as well. Once you have an API key, the process is relatively simple if you are familiar with python and APIs. If not, you can read some of the documentation from the link above or just copy and paste my simplified code while replacing my steamid with your own. Keep in mind that you should have your own API key as well and should never reveal that to anyone else. Thus, I access mine from a separate file. Here is my code:

{%- highlight python -%}
import pandas as pd
import requests

# Gets our API key
with open('steam_apikey.txt', 'r') as file:
    apikey = file.read()

# Set up the basic parts of the URL that we will use to access the API
base_url = 'http://api.steampowered.com/'
endpoint = 'IPlayerService/GetOwnedGames/v0001/?'
steamid = '76561198039160689'

# Put it all together, I also included a request to include the name of the game
url = base_url + endpoint + 'key=' + apikey + '&steamid=' + steamid + '&include_appinfo=true' + '&format=json'

# Gets the data
r = requests.get(url)

# The data comes out with the size as well, so we limit just to get the rows and columns in a usable format
steam_df = pd.DataFrame(pd.DataFrame(r.json()).values[1][0])

{%- endhighlight -%}

If you would like all of my code and the raw data, you can access that [here](https://github.com/DerebeWalton/Steam-Data.git).

# The Data
Now we get to the fun stuff. The Data itself!

## Summary Statistics

| Category                              | Time      |
| ------------------------------------- | --------- |
| Total Hours Played in Past 2 Weeks    | 11.62     |
| Average Hours Played for all Games    | 0.9       |
| Total Hours Play Since Account Created| 1757.75   | 

For reference, that last number of 1757.75 hours equates to about 73 days, which is about 2.44 months. So, I potentially have wasted 2 months for 24 hours per day on video games. For a full time job, that 219 8 hour days. This is starting to shame me a little too much, so let's move on. 

## Some Good Ol' Graphs
Now that we have some basic understanding of how much life I have spent on video games, we can explore a few more details on the games themselves.

For starters, we can explore the first question: "What proportion of games have I actually played out of my entire library?"

![Figure]({{site.url}}/{{site.baseurl}}/assets/img/steam_proportions.png)

Honestly, more than I expected. Granted, I imagine many of those games I have barely opened and likely only had open for less than an hour. On to the next graph!

---

We also wanted to know what the distribution looks like for my game time. In other words, of those games that I have played, how many have I played for a long time? A little time?

![Figure]({{site.url}}/{{site.baseurl}}/assets/img/steam_time_played.png)

As predicted after the first graph, there are a ton of games I have started playing and never really gotten into. Meanwhile, there are a few games I spend over 100 hours playing.

---

The positive skewness makes us wonder our next question: "What games have the most time played?"

![Figure]({{site.url}}/{{site.baseurl}}/assets/img/steam_top_10.png)

Well, in case you weren't aware, I do indeed love Star Wars. When 7 out of 10 of my top 10 are Star Wars games, I guess it indicates something. Something else we can notice is that Magicka, LEGO Star Wars, and Dungeon Defenders are all co-op games while most of the rest are singleplayer. I do enjoy both playing a good story game and enjoying a game with my wife.

---

While those might be my top games of all time, what about recently? As of today, here are the games I played and how much I played them in the past 2 weeks:

![Figure]({{site.url}}/{{site.baseurl}}/assets/img/steam_2weeks.png)

See, I don't *only* play Star Wars games. I also play Portal. And I may have played a little Star Wars Battlefront again. And for those who are wondering, no I do not have Star Wars: Outlaws yet because I still need to finish Star Wars: Jedi Survivor first. 


# What Now?

Overall, it looks like I love Star Wars video games, have spent a lot of time playing a lot of games, and still have many games left in my library to play if I ever get around to it.

But this is not the end! There is so much more for us to learn and study. For some more information on using APIs, check out [this page](https://www.dataquest.io/blog/python-api-tutorial/). If you feel like this was interesting and want to learn more about Steam, [here is](https://store.steampowered.com/) their main store page. If you already have a Steam account, check out [my code](https://github.com/DerebeWalton/Steam-Data.git) and try exploring your account.

What data would you want me to explore next?