---
layout: post
title:  "First Hackathon"
date:   2014-1-27 10:30:00
categories: jekyll update
---

This past weekend I went to my first hackathon, HackTech. While it wasn't exactly what I'd expected for it to be, it was an interesting experience ; by spending hours and hours in front of a computer, trying to learn new APIs/technologies/languages, I can definitely say that I learned a lot.

### My Real Project

Our project was to build a music-collaboration web-app that gave users a max of 20 minutes to work together in creating 20 seconds of sheet music (or 16 measures).

As we planned it out we had to deal with many questions, namely:

What library do we use for the notes and how do we map it to the sheet music?

How should the note-objects be structured and what attributes should be taken into consideration (frequency, length of beat, position in time, type of instrument, etc.)

How can we create web sessions for users to work together in real-time without lag or other difficulties?

And so on. We broke it up into three parts: frontend, backend/music libraries, and the "middleware" with which real-time would be enabled. I primarily focused on the last one.

#### Firebase

We worked with [Firebase](http://firebase.io), an API to store and sync data in real-time.

Firebase is really great because it eliminates the need for a database, and instead assigns each piece of data a unique identifier that you can use to access it later. This is also cool because it allows you to enable dynamic features on static pages (with a little JavaScript) by communicating with Firebase. Basically, JavaScript + Firebase = sweet.

In our project, each time a user placed a note onto the sheet music, a new Firebase reference was created. Not only did this make realtime an easy feature to have, it also kept a record of previous tracks built using the webapp, so we had a built in "log" of previous songs.

#### The rest

Besides that it was standard HTML + CSS, JavaScript, and deployment via Rails.

### Conclusion

Hackathons are pretty awesome. Also, Firebase is really cool, and I definitely plan on using it in the future.
