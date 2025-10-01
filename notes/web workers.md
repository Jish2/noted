---
updated: 2025-09-30T20:04
created: 2025-09-30T19:08
---
#language/javascript

way to run [[javascript]] scripts in background threads

>javascript is single threaded

processes will interrupt what is being rendered

> e.g. a large function
> 	the large function must complete before the UI can update
> 	[[web workers]] would be useful here

### use cases
In an [[electron]] app, you may want to use [[web workers]] to perform expensive calculations without interrupting UI updates