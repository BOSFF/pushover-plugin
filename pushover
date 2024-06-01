#!/usr/bin/python
# -*- coding: utf-8 -*-
r"""!
    ____  ____  ______       __      __       __       _____
   / __ )/ __ \/ ___/ |     / /___ _/ /______/ /_     |__  /
  / __  / / / /\__ \| | /| / / __ `/ __/ ___/ __ \     /_ <
 / /_/ / /_/ /___/ /| |/ |/ / /_/ / /_/ /__/ / / /   ___/ /
/_____/\____//____/ |__/|__/\__,_/\__/\___/_/ /_/   /____/
                German BOS Information Script
                     by Bastian Schroll

@file:        pushover.py
@date:        01.06.2024
@author:      Kevin Heidt
@description: Pushover Plugin
"""
import logging
import urllib.parse

from plugin.pluginBase import PluginBase

# ###################### #
# Custom plugin includes #
import asyncio
from aiohttp import ClientSession
import urllib
import http.client
# ###################### #

logging.debug("- %s loaded", __name__)


class BoswatchPlugin(PluginBase):
    r"""!Description of the Plugin"""
    def __init__(self, config):
        r"""!Do not change anything here!"""
        super().__init__(__name__, config)  # you can access the config class on 'self.config'

    def pocsag(self, bwPacket):
        r"""!Called on POCSAG alarm

        @param bwPacket: bwPacket instance
        Remove if not implemented"""
        poc_data = self.config.get("pocsag"),
        apicall = urllib.parse.urlencode({
            "title": self.parseWildcards(poc_data.get("title", default="{RIC}({SRICT})\n{MSG}")),
            "ric": self.parseWildcards(poc_data.get("ric", default="")),
            "text": self.parseWildcards(poc_data.get("message", default="{MSG}")),
            "priority": poc_data.get("priority", default="false"),
        })
        pass

conn = http.client.HTTPSConnection("api.pushover.net:443")
conn.request("POST", "/1/messages.json",
  urllib.parse.urlencode({
    "token": "a8266pghaesf82yd3kwfjv27h1ijqx",
    "user": "gtc9wcb585bzm537nfk2188bxgjw8c",
    "message": text,
    "priority": "2",
    "title": title,
  }), { "Content-type": "application/x-www-form-urlencoded" })
conn.getresponse()
