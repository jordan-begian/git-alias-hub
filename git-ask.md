# git ask

## What Does This Do?

When added to your .gitconfig file this alias will provide the following prompts to interact with when you enter `git ask` into your terminal

1. Commit Title:
2. Commit Description:
3. Commit? [y/n]

## How Does This Work? 

When you provide text as an input for the prompts and press `enter` or `return` the values that you proivded are used for submitting a commit in the following format. 

`git commit -m "example title text" -m "exmaple description text"`

## Why Would I Use This? 

Commit messages are intented to be short, sweet, and to the point regarding the change. However, sometimes you'd like to provide a bit more detail behind you change and that's totally possible!

This alias will provide you with an interactive way to add your title and description without having to write out the full git syntax written out above. 

⬇️ Which looks similar to this when looking over the commit history ⬇️

**add commit message title**  
and here is the description where you are able to provide a description if needed without having to worry about your message getting cut off in the history due to the length of the message

## Alias

```
ask = "!f() { \                                     
        read -p 'Commit Title: ' title && \         
        read -p 'Commit Description: ' desc && \    
        echo \"Title: $title\" && \                 
        echo \"Description: $desc\" && \            
        read -p 'Commit? [y/n]: ' confirm && \      
        if [ \"$confirm\" == \"y\" ]; then \        
            git commit -m \"$title\" -m \"$desc\"; \
        fi \                                        
    }; f"                                           
```
