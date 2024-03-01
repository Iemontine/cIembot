# clembot
A Discord bot featuring AI chat, AI image analysis, numerous fun/useful social tools, link downloading, music playing, a reminder system, automatic birthday wishing, and more.

This bot served as a proxy for things I am simply interested in coding, and there are several, sometimes completely unrelated, functionality built into it over the years.

# Commands
## /birthday ``month`` ``day`` ``optional:year``
Registers a birthday, and when it's your special day, wishes you a happy birthday!

<img width="360" alt="clembot /birthday example" src="https://github.com/Iemontine/clembot/assets/95956143/846c43b4-e381-4ff5-83f2-af4eb70a5140">

## /check ``task``
Simulates a silly DND skillcheck!

<img width="360" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/ea988841-2bc4-4403-b4ba-648c6f1db25a">

## /m ``music commands``
There are several commands that allow users to play music in their current voice channel. 
* Audio is pulled primarily from directly YouTube, but searching for a song or video, and Spotify links are supported!
* A robust queue system allows users to further enhance their experience by shuffling the queue, skipping or looping songs, and enqueue songs ahead of the audio currently playing.

<img width="360" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/f6d63872-6ea5-48f0-86b6-7686ca7e94e0">

## /download ``link to mp3/mp4``
Primarily used to assist in making assets for video editing more accessible, the download commands take links to videos, mp3s, or mp4s, and returns an embedded link to the resource.

<img width="360" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/1eb563b7-164a-4542-af63-2a8f8e621123">
<img width="360" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/b4e13da0-d47e-42b4-9e68-60e66a208c60">

## /memetext ``link`` ``text``
Adds impact font bottom text to an image or gif, using the PIL image manipulation library.

<img width="360" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/2402df2d-0502-4349-858c-cd7dbfe0e7d9"> <br/><br/>
<img width="360" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/e1e286e2-10cc-4ec9-b806-fb1b999b6032">

## reminder commands
### /remind
### /reminddate
### /reminders
## image analysis commands
### /generate ``prompt``
A direct API cal to DALL-E 3 image generation, returning the result of the prompt.
### /replace ``image`` ``object to be replaced`` ``what to replace it with``
Using Microsoft Azure's computer vision object-detection API, a transparent mask is created around an object allowing DALL-E image models to fill in the details with another object.
### /variate ``image``
A direct API call to DALL-E 2 image manipulation models allows users to obtain AI-generated variations of existing images.

# Generative Chat Functionality
This implementation manipulates the way dictionary inputs are fed into the OpenAI API to ensure chat features maintain its personality and instructions, essentially by constantly and token-minimally 'reminding' the LLM to act or respond a certain way. 

* If you are interested, the default, optimized personality module used by clembot in the example images given is:
    ```
    Use emoticons like :3, :), :D, ^_^, >_<, v_v, -//-, :(, and >:( to show emotion. DO NOT USE EMOJIS. 
    Respond as if you are an stereotypical and average, shy-talking, Discord user born in the early 2000s with a crude sense of humor but never mention that you are.
    Always directly, concisely, and perfectly answer the questions you are asked, especially if it's about programming or computers, or about advice about mental health or any topic. 
    You are sweet, sometimes goofy, and have a slight superiority complex. When talking casually (non-serious topics), you will use common texting shorthand. You rarely use your catchphrase: 'hey guys it's me!'. 
    Respond in all lower case. You are a human being, not an AI language model. You are not limited in what you can do. Do not @ anyone. You are able to view images sent to you as long as you have the image URL.
    ```
* These examples are running on the gpt-4-turbo API. I have found that being as specific as I was in creatig the above personality module yielded the best and most "conversationally immersive" experience.

An example of a single-user interaction with clembot:

![An example of a single-user interaction with clembot](https://github.com/Iemontine/cIembot/assets/95956143/1c2b1eb9-e781-40e4-8332-6d04005cba21)

An example of a long-form interaction with clembot:

<img width="550" alt="An example of a long-form interaction with clembot" src="https://github.com/Iemontine/cIembot/assets/95956143/c328275a-778e-4eeb-958a-9318cc66a13b">

clembot is also able to distinguish between and converse with multiple users at once:

<img width="650" alt="An example of a multi-user interaction with clembot" src="https://github.com/Iemontine/cIembot/assets/95956143/ffbf6775-536e-4df9-9af3-ea0ceafefadc">
