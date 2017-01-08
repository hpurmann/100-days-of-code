# 100 Days Of Code - Log

### Day 5: January 08, Sunday

**Today's Progress**: Progress! With a fresh mind, I knew the reason why source maps didn't work: They were disabled in my Chrome. By that time, I already upgraded to Webpack 2. Works out of the box. Then I found the problem with the dispatch of the "REPLACE" action as well. And in the end, I even found out why the selector was not working as I thought. I had to give it the sub-state where `yourchoice-redux` is mounted.

**Thoughts**: Feeling good that I fixed these. On the other hand – why was I making these mistakes in the first place? Maybe I shouldn't be coding at 2am.

**Link(s) to work**: 
* [Getting started with Webpack 2](https://blog.madewithenvy.com/getting-started-with-webpack-2-ed2b86c68783#.z8ffszi48)
* [Moving to Webpack 2](http://javascriptplayground.com/blog/2016/10/moving-to-webpack-2/)

### Day 4: January 07, Saturday

**Today's Progress**: Tried to connect the Items to the state so that their presentation reflects the current state (e.g. the turn blue when the state says they are selected). Fighing with the `getSelection` selector exported by `yourchoice-redux`. I can manually read the state and it's correct but with the selector, the array of selected elements is always empty. Tried to `yarn link` the `yourchoice-redux` module to make debugging easier. Webpack Hot Module Replacement doesn't seem to like that. Source Maps aren't working  either.

**Thoughts**: Pretty frustrating that this small piece of code is causing that much trouble. Something with the `bindToSelection` is not working as intended. Maybe it's even a bug in `yourchoice-redux` (though I doubt it).

**Link(s) to work**: _No link today_


### Day 3: January 05, Thursday

**Today's Progress**: Connected the React components to the Redux store to be able to dispatch actions based on user interactions (click, cmd+click, shift+click). Found a weird problem in the end when trying to use an exported selector from `yourchoice-redux` to get the array of currently selected items.

**Thoughts**: That went pretty smoothly. It's nice to see how to set up yourchoice in a really simple project. Feels harder than necessary though.

**Link(s) to work**: [react-redux](https://github.com/reactjs/react-redux)

### Day 2: January 04, Wednesday

**Today's Progress**: I added Redux (and the connection to the chrome devtools extension) to keep my selection state somewhere. This may seem overkill at first, I could just have used the internal state of the surrounding component. But I already know that I want to be able to display the last action in a separate section of the page. Transformed the components to be stateless and fixed linting issues while at it.

**Thoughts**: A bit boring to do but now, it will be pretty easy to connect the rendering with the state and dispatch actions on clicks.

**Link(s) to work**: [Redux Devtools Extension](https://github.com/zalmoxisus/redux-devtools-extension)

### Day 1: January 03, Tuesday

**Today's Progress**: Decided for a project. I want to tackle again creating a website to showcase the functionality of a library me and a coworker created. Its name is [Yourchoice](https://github.com/actano/yourchoice). I checked out what I did so far and upgraded the dependencies. 

**Thoughts**: It's great to work on this again. I want to give Yourchoice some publicity which is much easier if there is a demo page.

**Link(s) to work**: [Project repository](https://github.com/hpurmann/yourchoice-redux-example)
