import numpy as np
from PIL import ImageGrab
import cv2
import pytesseract
import pyautogui
import discord
from discord.ext import commands
import asyncio

description = '''Rust Anti-Raid Bot'''
bot = commands.Bot(command_prefix='!', description=description)
bot.raid_bot_channel = ''

# setting up OCR
pytesseract.pytesseract.tesseract_cmd = "C:\Program Files (x86)\Tesseract-OCR\\tesseract.exe"


@bot.event
async def on_ready():
    print("Started Rust Anti-Raid Bot")


@bot.command(name="antiraid", pass_context=True)
async def antiraid(ctx):
    """Returns version"""
    if ctx.message.author.id != '269430241246576641':
        return
    await bot.say('Rust Anti-Raid Bot. Version: alpha 2.0.\n"!antiraid-help" for list of commands.')


@bot.command(name="antiraid-help", pass_context=True)
async def antiraid_help(ctx):
    """Returns list of commands"""
    embed = discord.Embed(title="Anti-Raid Commands", color=0xff0000)
    embed.add_field(name="!antiraid", value="Returns current version", inline=False)
    embed.add_field(name="!antiraid-help", value="Returns list of commands", inline=False)
    embed.add_field(name="!antiraid-rules", value="Returns list of rules", inline=False)
    embed.add_field(name="!antiraid-channel", value="Changes notification channel to current channel", inline=False)
    embed.add_field(name="!antiraid-start", value="Starts Rust Anti-Raid Bot", inline=False)
    embed.add_field(name="!antiraid-screenshot", value="Takes a screenshot", inline=False)
    await bot.say(embed=embed)


@bot.command(name="antiraid-rules", pass_context=True)
async def antiraid_rules(ctx):
    """Returns list of rules"""
    embed = discord.Embed(title="Rules", color=0xac2a4c)
    embed.add_field(name="• No spamming (including advertising)", value=" \u200b", inline=False)
    embed.add_field(name="• Don't be rude or annoying", value=" \u200b", inline=False)
    embed.add_field(name="• English only", value=" \u200b", inline=False)
    embed.add_field(name="• No user bots", value=" \u200b", inline=False)
    embed.add_field(name="• No NSFW content allowed", value=" \u200b", inline=False)
    await bot.say(embed=embed)


@bot.command(name="antiraid-channel", pass_context=True)
async def antiraid_channel(ctx):
    """Changes notification channel to current channel"""
    await bot.say('Successfully changed notification channel to #' + ctx.message.channel.name)
    bot.raid_bot_channel = ctx.message.channel.id


@bot.command(name="antiraid-start", pass_context=True)
async def antiraid_start(ctx):
    """Starts Rust Anti-Raid Bot"""
    if bot.get_channel(bot.raid_bot_channel) is None:
        await bot.say('A notification channel has not been set. Please first set your notification channel with '
                      '"!antiraid-channel" in the channel you would like.')
        return
    await bot.say('Successfully started Rust Anti-Raid Bot')
    bot.loop.create_task(main())


@bot.command(name="antiraid-screenshot", pass_context=True)
async def antiraid_screenshot(ctx):
    """Takes a screenshot"""
    screenshot = ImageGrab.grab()
    screenshot.save('screenshot.png')
    await bot.send_file(ctx.message.channel, 'screenshot.png')


# sending message to discord
async def raid(message, channel):
    await bot.send_message(bot.get_channel(channel), message)


# checking if image text = 'respawn' with OCR
def process_img(grey_img):
    txt = pytesseract.image_to_string(grey_img)
    if txt == "Respawn":
        return True
    return False


# start rust anti-raid bot
async def main():
    await bot.wait_until_ready()

    food_counter = 0

    while True:
        # processing image to convert to different format, make it more readable for OCR and display the image
        img = ImageGrab.grab(bbox=(1490, 935, 1600, 970))
        img = np.array(img)
        img = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
        cv2.imshow('window', img)

        # if image text = 'respawn' call raid() function and end script
        if process_img(img):
            bot.loop.create_task(raid("You're being raided!", bot.raid_bot_channel))
            cv2.destroyAllWindows()
            break

        # end script if 'q' is pressed in cv2 window
        if cv2.waitKey(25) & 0xFF == ord('q'):
            cv2.destroyAllWindows()
            break

        food_counter += 1
        if food_counter == 720:
            pyautogui.keyDown('6')
            pyautogui.keyUp('6')
            food_counter = 0

        asyncio.sleep(5)

bot.run('insert token here')
