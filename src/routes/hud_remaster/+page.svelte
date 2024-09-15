<div class="main-content">
  <h1>CoD: WaW HUD Remaster for Black Ops 3 Zombies</h1>
  <div class="hlayout-spread">
    <div class="hlayout-column">
      <iframe
        width="1280"
        height="720"
        src="https://www.youtube.com/embed/cHBl0tvl23o"
        title="CoD: WaW HUD Port to Lua in Black Ops 3"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        referrerpolicy="strict-origin-when-cross-origin"
        allowfullscreen
      ></iframe>
      <style>
        p {
          text-align: left;
          width: 80%;
          max-width: 1000px;
        }

        h3 {
          text-align: left;
        }
      </style>

      <div class="hlayout-spread constrain-img-width">
        <div class="hlayout-column layout_img">
          <img src="/hud_original.png" alt="" class="img1" />
        </div>
        <div class="hlayout-column layout_img">
          <img src="/hud_original2.jpg" alt="" class="img1" />
        </div>
      </div>
      <h3 class="tight-header">Overview</h3>
      <p>
        This is a Call of Duty: Black Ops 3 mod that recreates the iconic HUD
        from the original zombies experience - World at War. World at War's HUD
        had many tiny details that were really difficult to nail. Getting it
        right was made even more difficult by the fact that Black Ops 3's custom
        Lua UI (LUI) system is <i>entirely undocumented</i> and modders weren't
        supposed to have access to it <i>at all.</i>
      </p>
      <h3 class="tight-header">Brief Technical Rundown</h3>
      <p>
        World at War's HUD used a menu system that no longer exists anywhere in
        the updated BO3 engine, so all the old HUD functionality had to be
        re-implemented from scratch using BO3's new UI system called LUI. LUI is
        pretty much just regular Lua, but it has a lot of custom engine
        integrations that connect it with the renderer and give it access to
        necessary game state. This system is much more powerful than the
        comparatively simple <code>.menu</code> files used in WaW. This new system
        has some issues for modders in particular, though. Unlike other parts Treyarch
        intended modders to tinker with, like gameplay scripting, LUI has no documentation
        and no available examples. In fact, the mod tools don't mention or acknowledge
        LUI's existance whatsoever, so modders are completely to their own devices.
      </p>
      <p>
        Despite this, I did eventually figure out how to get the game to load
        LUI - but its a lengthy discussion I'll save for later. Long story
        short, after reverse engineering the dumped lua files from the game and
        figuring out the UI system, I was able to finally start porting the old
        stuff to the new stuff. World at War's HUD is deceptively simple looking
        but there are tons of really tiny details that add to the unique look
        and feel. Getting them wrong, even slightly, would be a noticable
        letdown to other fans. One great example of this was the way the points
        don't snap instantly to the next value, they "scroll" over time to their
        new value. At the same time, each point-changing action results in the
        difference flying off to the side of the points bar. You can see this in
        the video above when I shoot zombies, there are yellow "+10"s shooting
        off semi-randomly while the points scroll to their new value over time.
        This took a LOT of time to get just right, because the existing
        animation system had no concept of how to animate between 2 textual
        values, but at the same time the way the game notifies the UI of the
        value change did not lend itself well to the nature of the problem
        either. Having documentation would have helped a ton, because I
        eventually discovered (in a muli-million line script dump) something
        called <code>LUI.UITimer</code> which takes a <code>interval</code> and
        a <code>on_tick</code> function, which was exactly what I needed to manually
        animate each frame of the text when the values changed. Digging through hundred-thousand
        line script dumps trying to piece together each part I needed to reach my
        goal was the typical workflow, but it got easier over time as I would remember
        more of the code I'd already seen and become familiar with the messy, tool-generated
        UI scripts. After a year-ish of working between classes, I completed a faithful
        recreation of every part of the WaW HUD!
      </p>

      <!--  <p>
        Despite its simple concept and appearance, this is actually one of the
        more complicated projects I've taken on. First of all, Black Ops 3 (BO3
        from now on) does have official mod tools - Treyarch gave us them a
        while after BO3's release, and they included Radiant Black (level/map
        editor) and the Mod Tools Linker, all of which come with some form of
        documentation and even Sublime Text grammars or scripting documentation.
        The linker is what builds your custom map, converts all your GSC scripts
        (CoD's custom scripting language), and bundles all your custom assets
        into a format the game can read called a fastfile. Unforunately, it
        doesn't even acknowledge lua scripts, which are necessary for building
        custom HUDS and menus. So we have no documentation, no intended way to
        add custom LUI scripts, but what do we have? BO3 actually ships with the
        HavokScript Lua VM and compiler inside the main executable, and it turns
        out you can get it to compile and run arbitrary lua scripts. 
      </p> -->
    </div>
  </div>
</div>

<style>
  p {
    text-align: left;
    width: 80%;
    max-width: 1000px;
  }

  h3 {
    text-align: left;
  }

  p {
    text-align: left;
    width: 80%;
    max-width: 1000px;
  }

  h3 {
    text-align: left;
  }

  .layout_img {
    margin: 0.2em;
  }

  .img1 {
    background-color: aliceblue;
    max-width: 100%;
    max-height: 1000px;
  }

  .constrain-img-width {
    max-width: 80%;
  }
</style>
