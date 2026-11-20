OverBubble is a plain JS library that provides pop-up chat style bubbles at a particular position on the browser window, while also trying to ensure the bubble stays within the boundary of the current veiwport.  OverBubble has many advanced features that lend itself to being used for story driven content or chat style applications right out of the box.  

Key features are:
* Different bubble styles are built in for common verbs, such as 'say' and 'yell'.
* Contains both conversational bubbles and "signs" for objects.
* Styles can be customized.
* Additional bubble verb functions and styles can easily be added.
* Chat bubbles can be absolute positioning (with easy updated) or attached to a DOM element

====================================
Initliazing targets
====================================
overbubble.set_target(<target name>,{target data},[{options}])

Target name is simply a string that will be used to connect chat target with bubble position and queue.
Target data is a hash, with the following three formats:
  Format 1 =>  {
    element: DOM element name,
    x: Offset x in pixels from DOM element,
    y: Offset y in pixels from DOM element,
  }

  Format 2 => {
    x: X screen pixel position for emitting point of bubbles,
    y: Y screen pixel position for emotting point of bubbles
  }

  Format 3 => {
    object:  Object that responds to .x and .y
  }

====================================
Built-in Chat Bubbles Types
====================================
Chat bubbles are simply a method call with the target name, the text to go into the bubble, and options to change defaults from those at initialization.

  overbubble.say(<target>,<text>,[{options}])
  overbubble.says(<target>,<text>,[{options}])
  overbubble.yell(<target>,<text>,[{options}])

Examples:
  overbubble.say('player','I don't know where I am...')
  overbubble.says('player','Maybe I am nowhere...and everywhere.')
  overbubble.yells('npc101','I have a stick! A very big stick!')
  overbubble.warn('sign_post','-- Tread lightly, the rabbit sleeps --')

If using with chat queues (or overStory), the chat bubbles are a verb in scripts, in the format:
  "[target] [bubble type]: [text in bubble] "

Examples:
  player says: I don't know where I am.
  player says: Maybe I am nowhere...and everywhere.
  npc yells: I have a stick! A very big stick!
  sign warn(s): -- Tread lightly, the rabbit sleeps --

Character "bubbles"
-----------------------------------------------------------------------------------
emote(s) - A text bubble that emits from target, but isn't said aloud
think(s) - A text bubble that expresses a thought, typically a cloud
# TODO - notice (think) - An alternative to think for styling, default style is the same
whisper(s) - A quit, hush style bubble
say(s) - Normal chat bubble.
exclaim(s) - A chat bubble styled of increased urgency or importance
scold(s) - An angry chat bubble
yell(s) - Attention grabbing, yelled chat bubble
happy - Chat bubble showing approval or success
love(s) - Romantic styled bubbled.  Default style is same as happy.

Object "bubbles"
-----------------------------------------------------------------------------------
info - A chat bubble styled more for objects than characters
warn(s) - Object styled bubble showing a warning
alert(s) - Object styled bubble showing an alert
success - Object styled bubble showing a successful message
