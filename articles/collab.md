---
title: Collaborative Coding Overview
published: false
tags:
- collaboration
---

This post will give you a general overview of how to get started with Collaborative Code Editing on the Nitrous.IO development platform.

### Start the Web IDE

Create a box on Nitrous.IO, or you can use a box that you've already created. Collaboration works on any box template.

In your list of boxes, click the IDE button to boot up the IDE for your box:

![Web IDE](/screenshots/ide-button.png)

### Adding Collaborators

Now we've got to give access to our friends / colleagues so they can access our box.

Note that with adding collaborators comes great responsibility. Notably, you *must trust* who you are adding to your box. For extra security, you should practice the following:

*Use SSH Key with passphrase*

If you've already added an SSH Key to Nitrous.IO without a passphrase, you'll need to delete it and re-generate one with a passphrase.

*Use HTTPS authentication with Github*

Using HTTPS authentication with Github should prompt you for your password, thus restricting any abuse from collaborators (but they're your friends, why would they do that?!). Better safe then sorry…my friends have done some evil things to my desktop background…and my forehead with a very, very permanent marker.

Okay, back to business. In the IDE, Click the "Collaborate" menu item in the top navigation, and select "Manage Collaborators":

![Collaborate Menu](/screenshots/collab/collab-menu.png)

A modal with a list of any collaborators you've already added will appear. Enter the _Nitrous.IO_ username, or email of the person you'd like to add to your box.

![Collaborate Modal](/screenshots/collab/collab-modal-email.png)

#### Nitrous.IO users & New Users

If you're inviting a user with their username, they'll receive an email and the box will appear in their list of boxes:

![Collaborate Modal](/screenshots/collab/shared-box.png)

If they don't have an account yet, they'll receive an invite to Nitrous.IO, and will be able to access only boxes to which they've been added as a collaborator.

### Collaborating on Files

Ok, now lets get to the good part. Once you and your collaborators have opened the IDE, you can edit files simultaneously.

First, and most importantly, you'll need to open the same file. Luckily, we put file status notifications in the chat window on the right of the IDE.

**Chat**

To open the chat, just click the little "message" icon on the right of the IDE. This will toggle the chat window which has a few valuable features.

![Online Users](/screenshots/collab/collab-online.png)

You can check who else is online by hovering over the group icon. Alternatively, you could just write a message in the chat saying "what's up", but sometimes people are around and are just ignoring you because you're not the most "likable guy"…bleh whatever, screw 'em.

**File status**

Assuming someone has joined the room and opened a file, you'll see a file status message in the chat window. This is a great shortcut to open the same file to start editing.

### Collaborate!

Finally, now that we have the same file open, we can collaborate. But wait…there's one more, incredibly important step. You'll need to actually turn "Collab Mode" on for each file.

To turn on Collab Mode, just click the little button on the top-right of the file:

![Collab Mode Button](/screenshots/collab/collab-button2.png)

Now, when you edit, your friend will see the changes happening live in their browser. They can type at the same time and it will show up in your browser.

This is really amazing when conducting remote interviews, when troubleshooting something for a friend, when pairing with someone across the globe, or just to make other geeky friends!
