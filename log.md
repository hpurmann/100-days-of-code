# 100 Days Of Code - Log

### Day 19: January 28, Saturday

**Today's Progress**: Learned about mutability in Rust. I want to change a value of a struct inside a vector. Now I create a completely new vector and copy over values by hand. This cannot be the right approach. Mapping over an iterator seems much better, but time's up for today.

**Thoughts**: The iterator article is pretty interesting, especially the difference between `iter()` and `into_iter()`.

**Link(s) to work**: 
* [Using iterators in Rust](http://hermanradtke.com/2015/06/22/effectively-using-iterators-in-rust.html)
* [Mutablility in Rust](https://doc.rust-lang.org/beta/book/mutability.html)


### Day 18: January 26, Thursday

**Today's Progress**: Added a function for printing the current gap word. The idea is to mutate the `revealed` flag of each digit in a gap word while playing. Maybe that's not the best idea because Rust is Immutable by default. Let's see ...

**Thoughts**: I'm soo slow. This is not surprising though. Having spend the last years in a dynamically typed language, I'm fighting with the compiler the whole time. Still worth it!

**Link(s) to work**: ["create new char rust" on Google](https://www.google.de/search?q=create+new+char+rust&oq=create+new+char+rust&aqs=chrome..69i64.1022j0j1&sourceid=chrome&ie=UTF-8)

### Day 17: January 25, Wednesday

**Today's Progress**: I started a new project: I want to explore the Rust language and play around with it. Therefore I decided to implement a simple Hangman game in Rust. Later, this topic could be expanded by implementing multi-user games or a web UI. Let's see how long until I'm bored.

**Thoughts**: I feel guilty to having skipped the last 4 days. I wasn't feeling that well. I think it's great to use Rust altough iterating over a string was harder than expected ;)

**Link(s) to work**: [Hangman Rust](https://github.com/hpurmann/hangman-rust)

### Day 16: January 20, Friday

**Today's Progress**: Got the list connected to the state. I initially dispatch an action for each item. Now I see the design flaw of the module a lot cleaner than I did in RPLAN: When I add or remove an item in my state, I need to also dispatch the action for `yourchoice-redux` to update the selection state. Problem is: The state is inconsitent (broken) in the time between the two dispatches. Items are already removed in my list but still marked as selected in yourchioce. In RPLAN, we solved this by explicity calling the reducer whenever we see actions which could change the iterable of selectable items. We essentially mark the action to be caught by this app-specific reducer. Some similar concept could be applied to `yourchoice-redux` itself.

**Thoughts**: This is good and bad at the same time. I learned something about our library building the demo page for it. But I also learned why the wrapper around the library may not be as good.

### Day 15: January 19, Thursday

**Today's Progress**: Tried to get the items into the state because I want to add buttons for adding and removing items. To do this in a clean way, i want to separate data (items by id) from the order (array of ids). This should usually be easy but I faced weird problems with `combineReducers` which just vanished after fiddling with it a bit.

**Thoughts**: Grmpf, I didn't push anything. Tomorrow, I should be able to make this work and be finished with the project. Finally. Seeking for something else already.

**Link(s) to work**: [`combineReducers`](http://redux.js.org/docs/api/combineReducers.html)

### Day 14: January 18, Wednesday

**Today's Progress**: I moved the website to a new orphaned branch inside the yourchoice repository. Then, I wrote a small publish script to publish to GitHub pages.

**Thoughts**: This was a bit tedious. Now I'm glad that everything works.

**Link(s) to work**: [Yourchoice on new GitHub pages](https://actano.github.io/yourchoice/)

### Day 13: January 17, Tuesday

**Today's Progress**: I added a component to show the current state. This way, developers know what data they get out of the libray.

**Thoughts**: This looks pretty helpful again. I think I'm already in the refinement process.

**Link(s) to work**: [Yourchoice with state inspector](http://hpurmann.com/yourchoice-redux-example/)

### Day 12: January 16, Monday

**Today's Progress**: Finally I added a meaningful description text on the right side. Though this is not coding, I had to do it because it provides huge value to the visitor.

**Thoughts**: This is getting somewhere! I'm already thinking about transferring these commits to yourchoice repository's `gh-pages` branch.

**Link(s) to work**: [Yourchoice with proper description](http://hpurmann.com/yourchoice-redux-example/)

### Day 11: January 15, Sunday

**Today's Progress**: I added a small description to a few of the API functions. They get displayed whenever they get called in the app. I'm thinking about adding the action payload as well.

**Thoughts**: I still need to somehow encourage the visitor to play around with the selection. I want to list what yourchoice is _not_.

### Day 10: January 14, Saturday

**Today's Progress**: Today I did a small improvement. I extended the item data with a name. This way, I can split the rendering of the id from the rendering of the name. Then I changed the rendering to use flexbox. I first thought I don't need to specify a width with flexbox. In the end, I chose percentage values.

**Thoughts**: The progress is ok. Custom React propTypes are nice. Static typing would be even nicer (though not required for such a small project). Splitting the data will be needed when I include it in the redux state.

### Day 9: January 13, Friday

**Today's Progress**: I managed to get the Grid layout of `react-bootstrap` working. Now I got a centered main column. The list is rendered with the Bootstrap `ListGroup` and `ListGroupItem`. I still have a problem with the focus pseudo-selector styling.

**Thoughts**: Not that much progress. I need to fill in the content and finish this project.

**Link(s) to work**: [Yourchoice with Bootstrap layout](http://hpurmann.com/yourchoice-redux-example/)

### Day 8: January 12, Thursday

**Today's Progress**: Because the basic functionality of the demo is done, I took the time to look into styling. People will get a more positive impression of the library if the demo page is visually appealing. A logo could be nice as well. I found the Bootstrap implementation for React.

**Thoughts**: Great that this library exists. The first impression is good. This way, I don't have to spend as much time on styling while still getting a proper result.

**Link(s) to work**: [React Bootstrap](https://react-bootstrap.github.io/)

### Day 7: January 10, Tuesday

**Today's Progress**: Today's work was dedicated to displaying the internal state of yourchoice. We now render the last action dispatched and the current anchor item. Additionally, some styles were enhanced.

**Thoughts**: The anchor is pretty helpful. The icon needs an explanation though.

### Day 6: January 09, Monday

**Today's Progress**: Configured Webpack to build a minified production bundle and decided to directly check it in into source control. It is considered an anti-pattern to host generated files. For pragmatically hosting something now, I decided to take this as the first approach.

**Thoughts**: Finally I got something out there. It's not pretty but it already works and shows how [`yourchoice`](https://github.com/actano/yourchoice) decides which items are selected.

**Link(s) to work**: [Hosted yourchoice demo](http://hpurmann.com/yourchoice-redux-example/)

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
