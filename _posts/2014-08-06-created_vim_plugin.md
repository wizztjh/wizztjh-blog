---
layout: post
title: Created a vim plugin then decided to donate to neovim
---

I decided to create a vim plugin to solve a repetitive task that me and my colleague always do at work. We would go to the top of the jasmine spec file and hightlight the description text, then copy and paste it to the browser as `http://localhost:3000/jasmine?spec=DataStore.Location`.  

This is an example of jasmine spec that we would need to open.

```coffeescript
describe 'DataStore.Location', ->
```

To write a function in Vimscript 
```coffeescript
function OpenJasmineRice()
endfunction
```

To grab the current line text
```coffeescript
let line=getline('.')
```

```coffeescript
execute "normal! gg?describe\<cr>N"
```

| code| |
---|---|
| `normal!` | execute in normal mode| 
|`gg` |(go to top of the file) |
|`?` |serach backward for describe|
|`\` |escape `<`|
|`<cr>`| enter (after /describe press enter) | 
| `N`| go back |


To call a function in command mode

```coffeescript
:call OpenJasmineRice()
```

Although 
```lua
Plugin.openJasmineRice = function()
  normal! gg?describe<cr>N
  line = getLine('.')
  
  
```
  
