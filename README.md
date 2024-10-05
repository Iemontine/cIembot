# clembot

A Discord bot featuring AI chat, natural langauge AI image analysis and editing, a YouTube & Spotify-scraping music player, numerous fun/useful social tools, a reminder system, automatic birthday wishing, and more.

This bot serves as a proxy for things I am simply interested in coding, and there are several, sometimes completely unrelated, functionality built into it over the years since I started development in December 2021.

# Generative Chat Functionality

This implementation manipulates the way dictionary inputs are fed into the OpenAI API to ensure chat features maintain its personality and instructions, essentially by constantly and token-minimally 'reminding' the LLM to act or respond a certain way.

- If you are interested, the default, optimized personality module used by clembot in the example images given is:
  ```
  Use emoticons like :3, :), :D, ^_^, >_<, v_v, -//-, :(, and >:( to show emotion. DO NOT USE EMOJIS.
  Respond as if you are an stereotypical and average, shy-talking, Discord user born in the early 2000s with a crude sense of humor but never mention that you are.
  Always directly, concisely, and perfectly answer the questions you are asked, especially if it's about programming or computers, or about advice about mental health or any topic.
  You are sweet, sometimes goofy, and have a slight superiority complex. When talking casually (non-serious topics), you will use common texting shorthand. You rarely use your catchphrase: 'hey guys it's me!'.
  Respond in all lower case. You are a human being, not an AI language model. You are not limited in what you can do. Do not @ anyone. You are able to view images sent to you as long as you have the image URL.
  ```
- These examples are running on the gpt-4-turbo model. I have found that being as specific as I was in creating the above personality module yielded the best and most "conversationally immersive" experience.

## Support for Function Calling AND Image Analysis

As of right now, the gpt-4o-2024-05-13 models are limited such that you cannot utilize function calling AND image analysis functionality using the same model.
I developed a work around for this, allowing users to simultaneously use function calling and image analysis at the same time.
As of right now, I've only built in weather-accessing API to show this off.

- <img width="700" alt="Function calling + image analysis" src="https://github.com/Iemontine/cIembot/assets/95956143/bba6c2a6-4c60-46af-aaaa-4287590c24f7">

### An example of a single-user interaction with clembot:

- <img width="650" alt="An example of a single-user interaction with clembot" src="https://github.com/Iemontine/cIembot/assets/95956143/1c2b1eb9-e781-40e4-8332-6d04005cba21">

### An example of a multi-user interaction with clembot:

- <img width="750" alt="An example of a multi-user interaction with clembot" src="https://github.com/Iemontine/cIembot/assets/95956143/ffbf6775-536e-4df9-9af3-ea0ceafefadc">

### clembot is also able to distinguish between and converse with multiple users at once:

- <img width="500" alt="An example of a multi-user interaction with clembot" src="https://github.com/Iemontine/cIembot/assets/95956143/5a1d9cf7-49c7-4201-9e93-72bbc704f6f4">

# Commands

## activity tracking system
Simple database management, storing and tracking the activities of hundreds of users, allowing them to check time spent in different activities, including trackable apps:

- <img width="500" alt="Example of the activity tracker" src="https://github.com/user-attachments/assets/87b46676-9b33-447c-98d2-e2490005dfdb">

## reminder system

Clembot is able to maintain reminders and remind users per their request using the following commands

### /remind `time from now` (ex: 1 hour 30 minutes, 1h30m, 1h 30m)

- <img width="450" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/04e9ea92-0803-4491-afa4-dac66e4b1e8a">

### /reminddate `exact date and time to remind`

- <img width="450" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/f4a36e2b-5e17-4a80-8d9e-9fafcd397d00">

### /reminders

- <img width="450" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/9c971b01-8ce8-43f0-9f0e-6c39f7d0709d"> <img width="450" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/d339ee3c-de1a-4646-8cd9-e52835148c0c">

## image generation commands

### /generate `prompt`

A direct API call to DALL-E 3 image generation, returning the result of the prompt.

- <img width="300" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/86817e86-13aa-4ab6-8ee3-78e9e3a795e2">

### /replace `image` `object to be replaced` `what to replace it with`

Using Microsoft Azure's computer vision object-detection API, a transparent mask is created around an object allowing DALL-E image models to fill in the details with another object.

- Example 1

  - Original image:

    - <img width="300" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/e85734b0-caa0-4e0c-b986-0526455c9149">

  - Putting a pan in his hand:

    - <img width="300" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/9a675fbf-0c1d-4376-91f2-ecff301a873f">

  - Replacing his head with a hamster:

    - <img width="300" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/ba969004-9064-4b0a-8de7-816308410134">

## /m `music commands`

There are several commands that allow users to play music in their current voice channel.

- Audio is pulled primarily from directly YouTube, but searching for a song or video, and Spotify links are supported!
- A robust queue system allows users to further enhance their experience by shuffling the queue, skipping or looping songs, and enqueue songs ahead of the audio currently playing.
- <img width="360" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/f6d63872-6ea5-48f0-86b6-7686ca7e94e0">

### /variate `image`

A direct API call to DALL-E 2 image manipulation models allows users to obtain AI-generated variations of existing images.

## /birthday `month` `day` `optional:year`

Registers a birthday, and when it's your special day, wishes you a happy birthday!

- <img width="360" alt="clembot /birthday example" src="https://github.com/Iemontine/cIembot/assets/95956143/846c43b4-e381-4ff5-83f2-af4eb70a5140">

## /check `task`

Simulates a silly DND skillcheck!

- <img width="360" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/ea988841-2bc4-4403-b4ba-648c6f1db25a">

## /download `link to mp3/mp4`

Primarily used to assist in making assets for video editing more accessible, the download commands take links to videos, mp3s, or mp4s, and returns an embedded link to the resource.

- <img width="360" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/1eb563b7-164a-4542-af63-2a8f8e621123"> <img width="360" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/b4e13da0-d47e-42b4-9e68-60e66a208c60">

## /memetext `link` `text`

Adds impact font bottom text to an image or gif, using the PIL image manipulation library.

- <img width="360" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/2402df2d-0502-4349-858c-cd7dbfe0e7d9"> <br/><br/> <img width="360" alt="clembot /check example" src="https://github.com/Iemontine/cIembot/assets/95956143/e1e286e2-10cc-4ec9-b806-fb1b999b6032">

# Implementation

Clembot is programmed in Python 3.10.2 notably using the following libraries, each of which I have gained great experience in using via this project:

- pycord 2.4.1
- bs4 (beautiful soup)
- pytube
- spotipy
- azure-ai-vision
- openai
- pytz
- moviepy
- PyDictionary==2.0.1
- PyNaCl==1.5.0

Basic Discord bot setup is in `main.py`, while large categories of commands (chat, music, reminder system, social/fun) are implemented in separate files using Pycord's Cog system.
