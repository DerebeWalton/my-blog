---
layout: post
title:  "Games Galore"
description: A post further exploring Steam games on the account of Gimotac, with a Streamlit app so everyone can use it!
image: /assets/img/streamlit.png
---
<p class="intro"><span class="dropcap">S</span>team, the biggest video game distributer on PC, has an API that allows users to retrieve some of their data about the games they play. In a previous post, we explored a few aspects, but now I create a Streamlit app to open up this data for anyone to have further easy exploration and learning! </p>

## Who Cares?

You likely don't really care about a random user's Steam game data. What this dataset and exploration really provides is a simple framework that can apply to many other potential datasets. Perhaps you have productivity data from your employees. With this framework, it can provide you ideas on exploring general trends and filtering, and even specific information for a given individual.

While the concepts can be applied elsewhere, I specifically explore this data set to deepen understanding of my video game habits and individual games in my library. A few specific questions I am looking to answer today is how much time I spend on my top games and whether certain games are played more on the Steam Deck or Windows, and what are the top on Windows vs Steam Deck. Now that the app is finished (although I can always improve my work) [here is a link](https://steam-explore.streamlit.app/) to the Streamlit app I have created. And [here is the code](https://github.com/DerebeWalton/Steam-Streamlit) for the app itself, including a csv file with the data.

While Streamlit looks really impressive, it does most of the heavy lifting for us, which I will show further down below. For now, we can look at some of the key insights from the data.

## Insights

Per both our [previous](https://derebewalton.github.io/my-blog/blog/Steam-Game-Habits/) and [current analysis](https://steam-explore.streamlit.app/), we can see that I play many Star Wars games. However, we now also include our Top 20 Games by playtime. As a result, we can see more information. Overall, the range from the top game to the 20th game is about 6000 minutes, or about 100 hours.

![Figure]({{site.url}}/{{site.baseurl}}/assets/img/all_top_20.png)

We can also look into specific games and see how much playtime for top performers are on Windows versus on the Steam Deck.

For our number one game in playtime, Star Wars: Battlefront 2 (Classic, 2005), the Steam Deck habing 69 minutes is knocked out when compared with the whopping 8,158 minutes on Windows. This drastic contrast is reflected if we look at the pie chart in our [app](https://steam-explore.streamlit.app/). 

![Figure]({{site.url}}/{{site.baseurl}}/assets/img/battlefront_pie.png)

But what I do with the app is not nearly as important as what *you* can do with it. 

## Streamlit App

As explained above, you can explore this dataset and Streamlit, but you can especially think about how other similar projects can help you learn, grow, and communicate effectively with these tools. As for the data itself, the app allows us to not only look at groups of top performers, but also individuals.

At the most basic level, you can look at the top games by playtime in a bar chart, like we did above. But you can also adjust both how many top performers you want and whether it is measured by all playtime, playtime on Windows, or playtime on the Steam Deck. Additionally, on this tab and the next tab, you can use a drop-down message to get a little insight about the nearby plot.

In the next tab, you can explore a specific game's information. This includes a table with the appid and playtime data as well as a pie chart for at-a-glance understanding. The only key issue here is that it requires the exact title of the game according to Steam, including symbols such as some trademark symbols. To aid you in ensurin the specific game title name, I also include one final tab with the data itself, so you can just copy and past the name of the game.

And, of course, buttons to adjust the number of games for the top results and the box for inputting a game title is in a convenient collapsable sidebar, so you can focus on your plots when really needed. What is really amazing, as I mentioned earlier, is that Streamlit is super easy to use. Here is my code for creating the sidebar:

{%- highlight python -%}
with st.sidebar:
    input_game = st.text_input('Enter a game title:')
    n_games = st.radio('Top ___ Games', [5,10,20])
    input_device = st.segmented_control("Filter played games by device", ['All', 'Windows', 'Steam Deck'])
{%- endhighlight -%}

So if you were worried about using Streamlit, you have no need to overstress yourself.

## Conclusion

None of this is groundbreaking, but we do not always have to explore crazy datasets. This analysis and app hopefully inspires you to go out and mess with this data and maybe even try your own. Let me know what your learn about my Steam account or what project you want to try! No matter what you choose to do, know that we can learn more every day. Take every opportunity you can to learn and enjoy life.