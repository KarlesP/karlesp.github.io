---
layout: page
title: Deadfish
---
## Introduction
First up, why-WHY would you want to learn Deadfish? There are so many languages and frameworks to work with, you can go outside and have fun for goodness sake...ok, fine, no FINE, I will tell you what I know about Deadfish but keep in mind that you can spend your life on this planet doing whatever you want.

So, Deadfish like almost every other esoteric languages is a joke language. It's more practical than Malbolge and it literally has 4 commands which are;

```
i #increment
d #decrement
s #square
o #output
``` 

and guess what...apperantly there is _NO INPUT COMMAND_. But no, let's assume that you want to write a program using this language because...reasons. So to write a Deadfish program you will need an interpeter, which you can probably find one in Python. But remember, it's useless even in theory.

So, without further ado here are some coding examples from the wiki;

## Code examples
Hello world (in ASCII numbers):
```
iisiiiisiiiiiiiioiiiiiiiiiiiiiiiiiiiiiiiiiiiiioiiiiiiiooiiio
dddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddo
dddddddddddddddddddddsddoddddddddoiiioddddddoddddddddo
```

The number 0:
```
diissisdo
```

The number 288:
```
iissisdddddddddddddddddddddddddddddddddo
```

And now it's the time for some implementations.

## Implementations

#### Lua
```
#!/usr/bin/env lua

accumulator = 0
while true do
    io.write(">> ")
    local input = io.stdin:read'*l'
    if accumulator == 256 or accumulator < 0 then accumulator = 0 end
    if input == "i" then
	accumulator = accumulator + 1
    elseif input == "d" then
	accumulator = accumulator - 1
    elseif input == "s" then
	accumulator = accumulator ^ 2
    elseif input == "o" then
	print(accumulator)
    end
end
```

#### Ruby
```
#!/usr/bin/env ruby
 
n = 0
while true
  print '>> '
  gets.chomp.each_char do |c|
    n = 0 if [-1, 256].include?(n)
    case c
      when 'd' then n -= 1
      when 'i' then n += 1
      when 'o' then puts n
      when 's' then n *= n
    end
  end
end
```



#### R
```
n <- 0
while(TRUE) {
  if(n==-1 || n==256) n <- 0
  cmd <- scan(n=1,what='character')
  fun <- switch(cmd,
                d=function(x) x-1,
                i=function(x) x+1,
                o=function(x) { cat(x,"\n"); x },
                s=function(x) x*x)
  if(!is.null(fun)) n <- fun(n)
}
```

## Epilogue
Does this need an epilogue? Fine! Deadfish is a joke language, there are other variations of that language like "Deadfish i" which is object oriented, "Functional deadfish" which adds functions and "Print "deadfish"" which prints characters but you can do whatever it does with about, yes, every other language. So in conclusion don't learn Deadfish, it's a waste of time.
