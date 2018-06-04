This is an ongoing list of scripting changes that have been implemented to scripting side of Tabletop Simulator.

######5/30/18 - v10.6.1

!!!info ""
    * Custom UI: 
        * Added getXmlTable() and setXmlTable() for dealing with Xml easier with Lua tables.
        * Changed setXml() from changing the actual Xml for the save file so everything is runtime changes only.
        * Changed getXml() to return the current Xml string including any runtime changes from setAttribute().
        * Fixed event recursion causing a potential lock up.
        * Fixed setXml() not working with empty string.
    * Scripting:
        * Added a 'debug_external_api' console command to show logging for external api messages.
        * Fixed logging an empty table throwing null.

######5/25/18 - v10.6

!!!info ""
    * Custom UI:
        * 3D UI added for objects (simialar to createButton/Input)
            * Each object can have its own assets (images)
            * Point scripting towards an object UI with `object.UI.setAttribute(...)`
            * Events called from an object's UI will automatically go to that object's Script. To override that feature and send it to Global, use `Global/functionName` for the attribute's name.
        * `UI.getXml()` and `UI.setXml()` added:
            * Allows for dynamic UI creation from a string
            * This OVERWRITES THE CURRENT XML on the target Global/object!!!
        * Click sounds added for inputs
        * Text universal attributes outlined in attributes section
        * getLookingForPlayers() added.
        * FIXED: Player colors now match TTS colors. For example, "red" is now equivalent to the player color red exactly.
        * FIXED: Dragging is improved so the element doesn't snap to its rectAlignment when dragged.
        * FIXED: When changing active attribute from script visibility would sometimes not work correctly
        
        

######5/9/18 - v10.5.1

!!!info ""
    * Custom UI:
        * Added UI.show(id) and UI.hide(id) for disabling and enabling ui with animations.
        * Now support the Image tag for custom images. 
        * Supports overriding the look of the UI using this custom image support.
        * Fixed visibility attribute not working correctly on elements with no id attribute or layout tag.
        * Fixed offsetXY set/getAttribute() not working.
        * Added Tooltip attribute for all objects

######5/7/18 - v10.5

!!!info ""
    * Addition of XML Custom UI and associated documentation as part of this documentation.
    * onSearchStart/onSearchEnd/onObjectSearchStart/onObjectSearchEnd added to Events.
    * The log() command's "label" and "tag" parameters were reversed to `log(object, label, tags)`
    * Scripted object button changes
        * The click_function of scripted object buttons now passes an argument for alt_click. This allows determining if anything besides left click was used on the button (like right click)
        * hover_color and press_color added as optional parameters
    * getJSON() and spawnObjectJSON() created.
    * Turns global static class added
        * Member variables for controlling how turns work
        * New event trigger for player turns beginning (onPlayerTurn)
        * Devalued previous onPlayerTurn events
    * Changelog moved under Getting Started due to the fact that it applies to the UI API as well as the scripting API. But I guess you figured that out already, didn't ya.
    * Added getJSON and spawnObjectJSON to Object/Base, respectively.
    

######3/26/18 - v10.4 Hotfix 2

!!!info ""
    * New Tabletop Simulator Scripting Documentation is created.
