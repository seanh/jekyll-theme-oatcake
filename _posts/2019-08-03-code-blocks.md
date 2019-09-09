Code Blocks, Syntax Highlighting and `<var>`
============================================

Code blocks use the [gruvbox colour scheme](https://github.com/morhetz/gruvbox).
Here's what a basic code block looks like:

    def test_validate_url_returns_an_http_url_unmodified():
        url = 'http://github.com/jimsmith'

        validated_url = validate_url(url)

        assert validated_url == 'http://github.com/jimsmith'

If a code block is too long it'll get a horizontal scrollbar, rather than
stretching the entire page:

    def test_validate_url_returns_an_http_url_unmodified():
        assert validate_url('http://github.com/jimsmith') == 'http://github.com/jimsmith'

You can use bold text in code blocks:

<pre><code>def test_validate_url_returns_an_http_url_unmodified():
    url = 'http://github.com/jimsmith'

    validated_url = <strong>validate_url(url)</strong>

    assert validated_url == 'http://github.com/jimsmith'</code></pre>

Syntax Highlighting
-------------------

To use Python syntax highlighting begin the code block with
<code>```python</code>.  For example this:

    ```python
    def test_validate_url_returns_an_http_url_unmodified():
        url = 'http://github.com/jimsmith'
        validated_url = validate_url(url)
        assert validated_url == 'http://github.com/jimsmith'
    ```

will render like this:

```python
def test_validate_url_returns_an_http_url_unmodified():
    url = 'http://github.com/jimsmith'
    validated_url = validate_url(url)
    assert validated_url == 'http://github.com/jimsmith'
```

Here's the [full list of languages supported](https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers)
for syntax highlighting.

You can also use [Jekyll's {% raw %}`{% highlight %}`{% endraw %} tag](https://jekyllrb.com/docs/liquid/tags/#code-snippet-highlighting)
for code highlighting, and this allows you to turn on line numbers with the
`linenos` option. For example: `{% raw %}{% highlight ruby linenos %}{% endraw %} ... {% raw %}{% endhighlight %}{% endraw %}`:

{% highlight ruby linenos %}
def foo
  puts 'foo'
end
{% endhighlight %}

Shell Scripts vs Shell Sessions
-------------------------------

<code>```shell</code> (or <code>```sh</code> <code>```bash</code>
<code>```ksh</code> or <code>```zsh</code>) is for highlighting shell scripts,
_not_ interactive shell sessions:

```sh
# Loop over every $python_version in the .python-version file.
while IFS= read -r python_version
do
    pyenv install --skip-existing "$python_version"
    if ! "$(pyenv root)/versions/$python_version/bin/tox" --version > /dev/null 2>&1
    then
        "$(pyenv root)/versions/$python_version/bin/pip" install --quiet --disable-pip-version-check tox > /dev/null
    fi
done < .python-version
```

For an _interactive_ shell session use <code>```console</code>,
<code>```terminal</code>, <code>```shell_session</code> or
<code>```shell-session</code>:

```terminal
$ git clone https://github.com/hypothesis/bouncer.git
Cloning into 'bouncer'...
warning: templates not found in /home/seanh/.config/git/template
remote: Enumerating objects: 1766, done.
remote: Total 1766 (delta 0), reused 0 (delta 0), pack-reused 1766
Receiving objects: 100% (1766/1766), 954.14 KiB | 2.16 MiB/s, done.
Resolving deltas: 100% (1044/1044), done.
$ cd bouncer
$ export DEBUG=yes                               # Turn on debug mode.
$ export HYPOTHESIS_URL="http://localhost:5000"  # The URL of the Hypothesis instance to use.
$ make dev
[2019-08-31 19:32:13 +0100] [17902] [INFO] Starting gunicorn 19.9.0
[2019-08-31 19:32:13 +0100] [17902] [INFO] Listening at: http://127.0.0.1:8000 (17902)
[2019-08-31 19:32:13 +0100] [17902] [INFO] Using worker: sync
[2019-08-31 19:32:13 +0100] [17905] [INFO] Booting worker with pid: 17905
```

Representing Variables with `<var>`
-----------------------------------

You can also represent the name of a variable by using [the `<var>` tag](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/var):

The variables <var>minSpeed</var> and <var>maxSpeed</var> control the minimum
and maximum speed of the apparatus in revolutions per minute (RPM).

Scrolling
---------

You can create a fixed-height `<pre><code>` with a vertical scrollbar by adding
the CSS class `scroll`. To do this in combination with syntax highlighting use
Kramdown's `{.some_class}` syntax to add the CSS class. For example:

    {:.scroll}
    ```python
    #!/usr/bin/python

    import sys
    import pygame
    from pygame.locals import *

    ...

    ```

Here's a large amount of Python code with a vertical scrollbar:

{:.scroll}
```python
#!/usr/bin/python

import sys
import pygame
from pygame.locals import *

import pacman
import util
import pills
import fruit
import waypoints
import redghost
import yellowghost
import pinkghost
import blueghost

class Game:
    "the object that controls the game"

    def reset(self):
        'Resets all game sprites and state variables'  
        #pacmans lives:
        self.nolives = 3
        self.maxlives = 3
        #the score
        self.score = 0 
        #has the level been won?    
        self.won = False
        self.wayobj = waypoints.Waypoints()
        self.allSprites = pygame.sprite.RenderUpdates()        
        self.pac = pacman.Pacman(self.wayobj)
        self.pacsprite = pygame.sprite.RenderUpdates() 
        self.pacsprite.add(self.pac)
        self.red = redghost.Redghost(self.pac,self.wayobj)
        self.yellow = yellowghost.Yellowghost(self.pac,self.wayobj)
        self.pink = pinkghost.Pinkghost(self.pac,self.wayobj)
        self.blue = blueghost.Blueghost(self.pac,self.wayobj)
        self.ghostsprites = pygame.sprite.RenderUpdates()
        self.ghostsprites.add(self.red)
        self.allSprites.add(self.red)
        self.ghostsprites.add(self.yellow)
        self.allSprites.add(self.yellow)
        self.ghostsprites.add(self.pink)
        self.allSprites.add(self.pink)
        self.ghostsprites.add(self.blue)
        self.allSprites.add(self.blue)
        self.pillobject = pills.Pills()
        self.allSprites.add(self.pillobject.pills)
        self.allSprites.add(self.pillobject.powerpills)
        self.fruitobject = fruit.Fruits()
        self.allSprites.add(self.fruitobject.fruit)
        self.scaredTimer = 0

    def startScreenLoop(self):
        'Runs the start screen loop until space is pressed'    
        hiScoresText = self.font.render('Hi Scores', True, self.hiScoreColor)
        pressSpaceText = self.font.render('Press Space to Start', True, self.instructionColor)
        madeByText = self.smallfont.render('Programmed by Sean Hammond in Python', True, self.smallTextColor)                   
        self.screen.blit(self.background, (0, 0))
        self.screen.blit(self.maze, self.mazecoords)
        self.screen.blit(madeByText, (self.screen.get_width()/100,self.screen.get_height() - (madeByText.get_height())))
        pygame.display.flip()

        #start screen loop:
        while True:
            self.clock.tick(60)
            for event in pygame.event.get():
                if (event.type == KEYDOWN):
                    if (event.key == K_SPACE):#(space bar)
                        start = True
                        return True
                    elif event.key == K_ESCAPE:
                        return False
                elif event.type == QUIT:
                        return False
            
            #update and draw everything to a new frame:
            self.allSprites.update()
            rectlist = self.drawAll(False)

            #draw text over the frame:    
            rectlist.append( self.screen.blit(hiScoresText, (self.background.get_width()/2-hiScoresText.get_width()/2,hiScoresText.get_height()*2)) )
            xcoord = hiScoresText.get_width()/2
            ycoord = hiScoresText.get_height()
            for x in range(1,11):
                text = self.font.render(str(x), True, self.scoreColor)
                rectlist.append( self.screen.blit(text, (xcoord, (ycoord*(2+x) ) )) )
            rectlist.append( self.screen.blit(pressSpaceText, (self.background.get_width()/2-pressSpaceText.get_width()/2, (ycoord*14))))

            #draw the new frame to screen:
            pygame.display.update(rectlist)

    def gameLoop(self):
        'Runs the game loop until pacman runs out of lives or eats all the pills'
        self.allSprites.add(self.pac)
        
        #Redraw the background, wiping everything from the screen:
        self.screen.blit(self.background, (0, 0))    
        self.screen.blit(self.maze, self.mazecoords)           
        #Draw the 'Score' text in the bottom-left (this only needs to be done once):
        text = self.font.render('Score: ', 1, self.scoreColor,(0,0,0))
        self.screen.blit(text, (22,562))
        #Update the screen with background and 'Score' text:
        pygame.display.flip()
                    
        #flags for which direction keys are currently held down:
        upturn = False
        downturn = False
        leftturn = False
        rightturn = False
        
        #Game loop:
        while True:
            self.clock.tick(60)

            #check for level complete:
            if len(self.pillobject.pills.sprites()) == 0:
                self.won = True
                return True        

            #Check for keyboard events, set turn flags or quit game:
            for event in pygame.event.get():
                if (event.type == KEYDOWN):
                    if event.key == 273: #up
                        upturn = True
                    elif event.key == 274: #down
                        downturn = True
                    elif event.key == 276: #left
                        leftturn = True
                    elif event.key == 275: #right
                        rightturn = True
                    elif event.key == K_ESCAPE:
                        return False
                elif (event.type == KEYUP):
                    if event.key == 273: #up
                        upturn = False
                    elif event.key == 274: #down
                        downturn = False
                    elif event.key == 276: #left
                        leftturn = False
                    elif event.key == 275: #right
                        rightturn = False
                elif event.type == QUIT:
                    return False

            #pacmans turn functions are called in every frame for which the relevant key is held down:
            if upturn:
                self.pac.turnUp()
            if downturn:
                self.pac.turnDown()
            if leftturn:
                self.pac.turnLeft()
            if rightturn:
                self.pac.turnRight()
        
            #call update() functions for animated sprites:
            self.allSprites.update()
            
            #check if pacman has eaten any pills, update score:
            eaten = pygame.sprite.spritecollide(self.pac, self.pillobject.pills, 1)
            if eaten:
                #each pill is worth ten points:
                self.score = self.score + 10*len(eaten)

            #check if pacman has eaten any power-pills, update score:
            eaten = pygame.sprite.spritecollide(self.pac, self.pillobject.powerpills, 1)
            if eaten:
                #each power-pill is worth fifty points:
                self.score = self.score + 50*len(eaten)
                #scare all the ghosts:
                self.scaredTimer = 5000
                for g in self.ghostsprites.sprites():
                    g.setScared()

            if self.scaredTimer > 0:
                self.scaredTimer = self.scaredTimer - 1
                if self.scaredTimer == 0:
                    #unscare all the ghosts:
                    for g in self.ghostsprites.sprites():
                        if g.mode == 'Scared':
                            g.setChase()
                
            #check if pacman has eaten any fruit, update score:
            eaten = pygame.sprite.spritecollide(self.pac, self.fruitobject.fruit, 1)
            if eaten:
                #each fruit is worth 500 points:
                self.score = self.score + 500*len(eaten)
                             
            #check if pacman has collided with any ghosts, kill pacman or kill ghosts:
            eaten = pygame.sprite.spritecollide(self.pac, self.ghostsprites, 0)
            if eaten:
                for g in eaten:
                    if g.mode == 'Eaten':
                        continue
                    if g.mode == 'Scared':
                        g.setEaten()
                    else:
                        if not self.pac.dead:
                            self.pac.setDead()
                            self.nolives = self.nolives - 1
                            if self.nolives < 0:
                                return True             

            rectlist = self.drawAll(True)
            #draw the new frame to screen:
            pygame.display.update(rectlist)

    def drawAll(self,inGame):
        'draws all changes for this frame and updates the screen, the parameter decides whether pacmans score and lives get drawn'
        #Collect all visual changes for the new frame in rectlist:
        #the pills
        self.allSprites.clear(self.screen,self.background)
        rectlist = (self.allSprites.draw(self.screen))
        rectlist.append(self.screen.blit(self.maze, self.mazecoords))
        if inGame:
            #pacmans lives
            xcoord = 400 #TODO get rid of hardcoded coords
            ycoord = 563
            for x in range(0,self.maxlives):
                rectlist.append( self.screen.blit(self.missingLife,(xcoord,ycoord)) )
                if x < self.nolives:
                    rectlist.append( self.screen.blit(self.pac.frames[0],(xcoord,ycoord)) )              
                xcoord += 30
            #the score
            text = self.font.render(str(self.score), 1, self.scoreColor,(0,0,0))
            rectlist.append( self.screen.blit(text, (100,562)) ) 
        return rectlist           

    def play(self):
        "the games controlling function - handles initialisation and the main loop"
        #Initialize pygame:
        pygame.init()
        self.screen = pygame.display.set_mode((500, 600)) #window size fixed & hardcoded for now
        pygame.display.set_caption('python pacman!')

        #Create the games text colors:
        self.scoreColor = (255,195,24)
        self.hiScoreColor = (206,138,0)
        self.instructionColor = (41,182,82)
        self.smallTextColor = (0,101,49)
        #Create the games fonts:
        self.font = pygame.font.Font(None,30)
        self.smallfont = pygame.font.Font(None,20)
        self.missingLife = util.load_image('pacman11.png')
 
        self.background = pygame.Surface(self.screen.get_size())
        self.background = self.background.convert()
        self.background.fill((0, 0, 0))

        self.maze = util.load_image('maze.png', -1)
        self.maze = self.maze.convert()
        self.mazecoords = (15,22)

        self.clock = pygame.time.Clock() #the clock used for frame timing

        #Main loop
        while True:
            #Reset and enter the startscreen loop:
            self.reset()
            result = self.startScreenLoop()

            if (result == False): #the user pressed Exit while on the start screen
                return
        
            #After leaving the start screen reset and enter the game loop:
            self.reset()
            result = self.gameLoop()
            if (result == False): #the user pressed Exit while in the game
                return
            
            #After exiting the game loop, check if pacman won or lost and display result:
            if self.won:
                text = self.font.render('Well Done', 1, self.hiScoreColor)
            else:
                text = self.font.render('Game Over', 1, self.instructionColor)
            self.screen.blit(text, (200,252))
            pygame.display.flip()

            #Secondary loop, hold everything still while result is displayed"
            exit = False
            for x in range(0,500):
                self.clock.tick(60)
                for event in pygame.event.get():
                    if (event.type == KEYDOWN):
                        exit = True
                if exit:
                    break

            #Remove pacman from allsprites:
            self.allSprites.remove(self.pac)

def main():
    gameobj = Game()
    gameobj.play()

#this calls the 'main' function when this script is executed
if __name__ == '__main__': main()
```
