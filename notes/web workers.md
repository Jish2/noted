#language/javascript

way to run [[javascript]] scripts in background threads

"javascript is single threaded" (can you import this from javascript page

processes will interrupt what is being rendered

> e.g. a large function
> 	the large function must complete before the UI can update
> 	[[Web Workers]] would be useful here

### use cases
In an [[electron]] app, you may want to use [[Web Workers]] to perform expensive calculations without interrupting UI updates