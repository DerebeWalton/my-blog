---
layout: post
title:  "Too Many Games, Too Little Time"
description: Exploring a dataset of Steam games from user Gimotac
image: /assets/img/Gimotac_Account.png
---
<p class="intro"><span class="dropcap">H</span>ow we spend our free time is important. Depending one what we do, it can bring us closer to or farther from our loved ones, increase or decrease our stress, or many other things. For me, I occasionally enjoy relaxing by playing video games on my own and with my wife. Steam is the biggest video game distributor on PC. If you play any PC game besides Minecraft, Fortnite, or Microsoft Solitaire, you likely have Steam installed and at least a few games in your Steam Library. For me, I have over 300 games on Steam and love playing on my Steam Deck that my wife got me for Christmas last year. As we explore my Steam library showing how I spend some of my time, I hope you find this interesting and can reflect on how you spend your free time.</p>

# Why Do I Care?
Since discovering this API, I wanted to explore my Steam library data more closely than just what Steam shows on my profile page. Some specific questions include what proportion of games have I actually played out of my entire library, what games have I played the most (while excluding Terraria, since I used to share this account with my brother and he racked up over 450 hours on that game), and how much of recent games I have played.

# Ethics
In much of data science, we would use data that is provided to us by an employer or contractor. When using data from other places, there may be rules and policies to which we agree so we can access and use said data. In all cases, we must be careful in how we handle the data to follow those rules and to respect the privacy and security of ourselves and others. With this data specifically, I signed up with Steam's API and received an API key. Part of Steam's policy is that I can only access the data of a given account with permission from the account owner. Naturally, since I am the account owner, I have my own permission to use it. Please be mindful when collecting and using data in your Data Science journey.
*I should note here that this is personal data and while you are welcome to view the information found in this blog post and related links, I do not give permission to view my Steam account data through the Steam API*

# How Would You Get This Data?
To get this data, as previously mentioned, I signed up for Steam API access and received a Steam API Key. You can do this as well by filling out this form referenced on the [Steam Web API Documentation](https://steamcommunity.com/dev) page, which also has references for accessing other data as well. Once you have an API key, the process is relatively simple if you are familiar with python and APIs. If not, you can read some of the documentation from the link above or just copy and paste my simplified code while replacing my steamid with your own. Keep in mind that you should have your own API key as well and should never reveal that to anyone else. Thus, I access mine from a separate file. Here is my code:

{%- highlight python -%}
import pandas as pd
import requests

with open('steam_apikey.txt', 'r') as file:
    apikey = file.read()

base_url = 'http://api.steampowered.com/'
endpoint = 'IPlayerService/GetOwnedGames/v0001/?'
steamid = '76561198039160689'

url = base_url + endpoint + 'key=' + apikey + '&steamid=' + steamid + '&include_appinfo=true' + '&format=json'

r = requests.get(url)

steam_df = pd.DataFrame(pd.DataFrame(r.json()).values[1][0])

{%- endhighlight -%}

# The Data

# What Now?
If you feel like this was interesting and want to learn more about Steam, 
check your own account
what data would you want me to explore next?