Quickstart
==========

This page gives a brief introduction to the package and its simplest form of usage. Everything on this page assumes you have the package installed, if you don't please follow the steps in the :doc:`installing` portion.

*******************************
1. Import the required packages
*******************************

.. code-block:: python
  
  import discord
  from discord.ext import commands
  from shopipy import Shop, ShopPage, ShopItem

*****************************
2. Create a simple bot client
*****************************
For more information regarding this step, please refer to `this <https://discordpy.readthedocs.io/en/latest/quickstart.html/>`_

.. code-block:: python


  client = commands.Bot(
      command_prefix="BOT_PREFIX_HERE",
      intents=discord.Intents.all()
  )

  @client.event
  async def on_ready():
      print("All shops online!")

  client.run("BOT_TOKEN_HERE")

*********************
3. Create the command
*********************

.. code-block:: python

  @client.command()
  async def shop(ctx):
      # define global information for the shop
      shop = Shop(
          title = "Grocery Store",
          currency = "$"
      )

      # define items for the shop
      cereals = [
          ShopItem(
              id = "rice_krispies",
              name = "Rice Krispies",
              description = "Rice Krispies is a light and crispy breakfast cereal made from toasted rice",
              price = 10,
              category_id = "cereal"
          ),
          ShopItem(
              id = "lucky_charms",
              name = "Lucky Charms",
              description = "Lucky Charms is a colorful breakfast cereal featuring frosted oats and marshmallow shapes, each representing a different magical charm",
              price = 20,
              category_id = "cereal"
          ),
      ]

      # define shop page for the items
      cereal_page = ShopPage(
          shop = shop,
          title = "Cereals",
          items = cereals,
          description = "A collection of our finest oats and wheat",
          footer = "The cake is a lie..."
      )

      # send a message containing the shop 
      await ctx.send(embed = cereal_page.embed, view = cereal_page)
```
