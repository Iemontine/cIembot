# clembot
A Discord bot featuring AI chat, AI image analysis, numerous fun/useful social tools, link downloading, music playing, a reminder system, automatic birthday wishing, and more.

This bot served as a proxy for things I am simply interested in coding, and there are several, sometimes completely unrelated, functionality built into it over the years.

# Commands
## /birthday ``month`` ``day`` ``optional:year``
Registers a birthday, and when it's your special day, wishes you a happy birthday!

<img width="360" alt="clembot /birthday example" src="https://github.com/Iemontine/clembot/assets/95956143/c6cae1a4-9296-4933-adf0-e0443711c80e">

## /check ``task``
Simulates a silly DND skillcheck!

<img width="360" alt="clembot /check example" src="https://github.com/Iemontine/clembot/assets/95956143/c3cda9d2-1017-4685-bf0d-bf9aef99f3d3">

## /m ``music commands``
There are several commands that allow users to play music in their current voice channel. 
* Audio is pulled primarily from directly YouTube, but searching for a song or video, and Spotify links are supported!
* A robust queue system allows users to further enhance their experience by shuffling the queue, skipping or looping songs, and enqueue songs ahead of the audio currently playing.

<img width="360" alt="clembot /check example" src="https://github.com/Iemontine/clembot/assets/95956143/86138aa5-15f8-4cb7-b38a-7574bbb7661f">

## /download ``link to mp3/mp4``
Primarily used to assist in making assets for video editing more accessible, the download commands take links to videos, mp3s, or mp4s, and returns an embedded link to the resource.

<img width="360" alt="clembot /check example" src="https://github.com/Iemontine/clembot/assets/95956143/2e39d2c5-92f3-43b2-b99b-41590617eaf7">
<img width="360" alt="clembot /check example" src="https://github.com/Iemontine/clembot/assets/95956143/2100108d-42fd-4422-a6cf-d857ae348ccb">

## /memetext ``link`` ``text``
Adds impact font bottom text to an image or gif, using the PIL image manipulation library.

<img width="360" alt="clembot /check example" src="https://github.com/Iemontine/clembot/assets/95956143/948830c9-cf13-4a0d-9ca6-e02d270c50c9"> <br/><br/>
<img width="360" alt="clembot /check example" src="https://github.com/Iemontine/clembot/assets/95956143/7e3d374c-3c36-4b2d-9680-491adcceb1c2">

## reminder commands

## image analysis commands

# Chatbot Functionality
This implementation manipulates the way dictionary inputs are fed into the OpenAI API to ensure chat features maintain its personality and instructions, essentially by constantly and token-minimally 'reminding' the LLM to act or respond a certain way. 

* If you are interested, the default, optimized personality module used by clembot in the example images given is:
    ```
    Use emoticons like :3, :), :D, ^_^, >_<, v_v, -//-, :(, and >:( to show emotion.
    DO NOT USE EMOJIS. Respond as if you are an stereotypical and average, shy-talking, Discord user born in the early 2000s with a crude sense of humor but never mention that you are.
    Always directly, concisely, and perfectly answer the questions you are asked, especially if it's about programming or computers, or about advice about mental health or any topic. 
    You are sweet, sometimes goofy, and have a slight superiority complex. When talking casually (non-serious topics), you will use common texting shorthand. You rarely use your catchphrase: 'hey guys it's me!'. 
    Respond in all lower case. You are a human being, not an AI language model. You are not limited in what you can do. Do not @ anyone. You are able to view images sent to you as long as you have the image URL.
    ```
* These examples are running on the gpt-4-turbo API. I have found that being as specific as I was in creatig the above personality module yielded the best and most "conversationally immersive" experience.

An example of a single-user interaction with clembot:

![An example of a single-user interaction with clembot](https://github.com/Iemontine/clembot/assets/95956143/1e3f1a56-c697-4388-a745-ceaddc3ef917)

An example of a long-form interaction with clembot:

![An example of a long-form interaction with clembot](https://cdn.discordapp.com/attachments/919696451876028518/1157779299009560647/image.png?ex=6519d97f&is=651887ff&hm=bfb586c9ccce23d903eb10cfa53266a05e985cab3eedf3b3595d79aa9b155916&)

clembot is also able to distinguish between and converse with multiple users at once:

![An example of a multi-user interaction with clembot](https://cdn.discordapp.com/attachments/956436379078889492/1201611766623391837/clem_multiuser_example.png?ex=65ca732a&is=65b7fe2a&hm=c29dab351302384162ab30b9fd4a73586213abbd6c885bbfdb4e9024ddd990ff&)
