Welcome to AsyncBattlerite's documentation!
===========================================
Basic Usage::

   import aiohttp
   import asyncio
   import asyncbattlerite

   loop = asyncio.get_event_loop()
   brc = asyncbattlerite.BRClient('your-api-key')

   # You can also provide an aiohttp.ClientSession to the BRClient constructor
   session = aiohttp.ClientSession()
   brc_a = asyncbattlerite.BRClient('your-api-key', session)

   # Get 3 matches after specified time
   # after and before can also be datetime.datetime objects
   matches = loop.run_until_complete(brc.get_matches(limit=3, after="2017-11-22T20:34:58Z"))

   # Go to the next pages of matches
   loop.run_until_complete(matches.next())

   # Get telemetry data for one of the matches
   telemetry = loop.run_until_complete(matches.matches[0].get_telemetry())


asyncbattlerite.BRClient
------------------------

.. automodule:: asyncbattlerite.brclient
    :members:
    :show-inheritance:

asyncbattlerite.Models
----------------------

.. automodule:: asyncbattlerite.models
    :members:
    :show-inheritance: