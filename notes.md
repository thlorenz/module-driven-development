# 0
- modularity and why it is important
- convince you of this by showing theoretical and practical benefits

- theoretical ones taken from a book I read recently
- enables collaboration, bug fixes, easier reuse (smaller features)
- use replpad as an example

# 1 
- 10 year old book, more relevant than ever READ IT!
- promotes the importance of modularity related to software development
- modularity not a new idea as the following quotes show

#2 
- by module we mean an npm module (published)
- obvious way to achieve this on a package level, is to to split them up into lots of smaller packages
- introduce connect

##2.2
  Connect didn't start out this way. Most of these were part of the framework.
  The result of a very disciplined effort of pulling modules out of connect.

##3 What constitutes a Module
-- roll out tweets
- application specific logic is hard to be make reusable and mostly is coupled
- need good reason to NOT publish instead of the other way around

#3 Easier Said Than Done
-- 1
- benefits are you end up with smaller modules, easier to understand
- separately tested, separately useable
- forced to write readme, which results in detailed module documentation, motivation to help others as well
- you'll need it for some other lib soon enough (speak from experience)
- learning curve minimal (doesn't do much) and simple API
- module does one thing

-- 2
- single functions can easily be understood and reused
- hoogle: input - output based search
- hoogle: String -/ String "map string to another"
- unfortunately functions combined into big libs and with deficient cabal you are in dependency hell once a week

##3.1 Challenges
-- 2
- related (hard to see that coupled functions can be standalone)

##3.2 Patterns
--1
- building small modules helps in spotting them and they are less work to publish
- chance of coupling is smaller since they do less - need less dependencies 

--2
- hardest part - techniques involved are inversion of control, i.e. with help of events (example shown)

--3
- get used to it, discipline, becomes natural

--4
- easier once they are in separate file already
- slows you down since publishing needed, but worth it
- on the other hand you can make it do the least you need at the moment, test and publish (Prototype)
- you, with help of community can expand on features and implementation

#3.3 Pull Out Process
--1
- the more often you do this, the faster this gets

--2
- no one will use your lib if you cannot prove that it works

--3
- show'em that it CURRENTLY works

--4
- some shops cannot use a module if it doesn't clearly state its license (MIT or BSD will do)

--5
- I myself have thanked myself many times for writing a good readme

--6
- will be using more npm modules, need to be able to learn how to use them quickly

--7
- pick nice name here

#4
- piping
- scriptie-talkie
- vim-bindings
- vim-map
- source code
- core docs

#6 AnsiColors

##6.1
- once pulled out added background colors
- in the process created ansistyles module, even smaller
- kept it separate since styles are not the same as colors

#7 Hermit
- wanted to show core dox in repl
- nodejsapi exposes dox as json, but desc is html

##7.3 fs.readfile screenshot
- started inside replpad to implement simple html parser (i.e. just remove tags)
- once realized that this is bigger, created hermit
- now you can: curl http://nodejs.org/api/assert.html | hermit
- not too pretty, but useful for smaller snippets (more colorful than `lynx --dump`)
- oh, if ansicolors and ansistyles would have been part of replpad, hermit couldn't have used it

#8 Readline-Vim
- started as plugin to replpad
- part of replpad code base for long time

#8.1
- took repl as an argument since that is what I applied vim bindings to
- realized that actually it added it to just the underlying readline

#8.2
- all I have to do is just pass in rli

#8.3
- state part of replpad, also I had planned to do certain things when switching between modes
- impossible to separate? NO

#8.4
- point out emitted events

#8.5
- added tons of tests
- created readline test harness to help with these (as separate module of course)
- improved the documentation
- added vim like mappings
- very good I pulled it out, can now be applied to any readline

#9 Scriptie-Talkie
- more feedback for replpad, but is separate thing (evaluates snippets in isolation)
- separate command line tool (run it on a file)
- with help of browserify made it work in browser

--1
- and can embed it -- fix code ;)

--2
- did not want to rewrite rendering code (right side)
- problem to port cli tools to browser
- instead of murking with scriptie-talkie code - solve this general problem so it will benefit other projects as well

#10 How to become Module Driven

--1
- by standalone I mean, it is not attached to a prototype, modify state, etc.,

--2  
- can you think of any other use case than yours? Yes, so pull it out.

##10.1
--1

--2
- easier to document, test and improve it
- easier to collaborate
- easier to understand than huge code bases

##10.2
--1
- or copy your package.json

--2
- including travisify badge

--3
- allows developing dependents and dependees side by side and proofing a separate module before publishing it
