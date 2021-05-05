# slackbot
A simple bot to interact with Slack
```python
from datetime import datetime
from slack.web.classes.objects import TextObject

from .slackbot import SlackBot
from .slack_message import SlackMessage


bot = SlackBot(token=token)
channel_name = 'Test'

message = SlackMessage(
    title='Hello, World!',
).add_context(
    elements=[TextObject(text=':calendar: {}'.format(datetime.now()),
                         subtype='mrkdwn')],
).add_section(
    text=':newspaper: *Just a testing string*',
).add_context(
    elements=[TextObject(
        text=':pushpin: Another testing string',
        subtype='mrkdwn',
    )],
).add_divider()
bot.chat_post(
    channel=channel_name,
    message=message,
)

```

<p align="center">
  <img src="https://raw.githubusercontent.com/lehoa1806/slackbot/main/slack.png">
</p>
