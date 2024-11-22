# Neko Example Plugin Format

## Advanced: Decorators
```python3

from NekoRobot.modules.helper_funcs.decorators import neko_cmd
from telegram import Update
from telegram.ext import CallbackContext

@neko_cmd(command='hi', pass_args=True)
async def hello(update: Update, context: CallbackContext):
    message = update.effective_message
    message.reply_text("hello")

    
__mod_name__ = "Hi"
__help__ = """
<b>Hi</b>
- /hi: Say Hello There
"""
```



## Advanced: Pyrogram
```python3
from NekoRobot import pgram

Neko_PYRO_Hello = filters.command("hi")

@pgram.on_message(Neko_PYRO_Hello) & ~filters.edited & ~filters.bot)
async def hmm(client, message):
    j = "Hello there"
     message.reply(j)
    
__mod_name__ = "Hi"
__help__ = """
<b>Hi</b>
- /hi: Say Hello There
"""
```

## Advanced: Telethon
```python3

from NekoRobot import tbot
from NekoRobot.events import register

@register(pattern="^/hi$")
async def hmm(event):
    j = "Hello there"
     event.reply(j)
    
__mod_name__ = "Hi"
__help__ = """
<b>Hi</b>
- /hi: Say Hello There
"""
```

## Advanced: PTB
```python3

from NekoRobot import NEKO_PTB
from telegram import Update
from telegram.ext import CallbackContext, CommandHandler

async def hi(update: Update, context: CallbackContext):
    j = "hello"
    update.effective_message.reply_text(j)

HANDLER = CommandHandler("hi", hi, block=False)
NEKO_PTB.add_handler(HANDLER)

__handlers__ = [ HANDLER, ]
    
__mod_name__ = "Hi"
__help__ = """
<b>Hi</b>
- /hi: Say Hello There
"""
```
