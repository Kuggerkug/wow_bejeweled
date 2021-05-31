# wow_bejeweled
bejeweled fix for BC Classic 2.5.1

forked off of the version posted on github by Nighthawk42

Per Cassini from warcrafttavern:

What kills most addons is a change in the API where functions to create “backdrops” and “backdrop colors” have been remove. To fix it, developers have to create frames that extend the BackdropTemplateMixin and “BackdropTemplate”, then the old functions work again. See below for an example:

before:
local frame = CreateFrame("EditBox", name, parent)

after:
local frame = CreateFrame("EditBox", name, parent, BackdropTemplateMixin and "BackdropTemplate")

In the case of Bejeweled, I went through Bejeweled.lua and changed any CreateFrame call that had just 3 parameters and added the last 2.  There might have been, oh I dunno, 50 frames that were changed.  Also updated the TOC to 2.5.1
