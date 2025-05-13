Title: A little something to get you started
Difficulty: Trivial
Skills: Web
Flags: 1

# Walkthrough
Opening the challenge brings you to this page:
![[Pasted image 20250513130645.png]]
... Wow, not a lot to go on.

Well we can start with vulnerability analysis, setting up our proxy, port scanning, banner grabbing, or....
Let's open up the source code

With a page like this, it shouldn't be too difficult to go through

Right Click -> View Page Source brings me to this page:
![[Pasted image 20250513131054.png]]
I see it uses a background image of "background.png"
the `<style></style>` tags let me know that this is embedded CSS. I also know 2 things from the "background.png"
1) It is suspicious because there is no background on the page, yet a background image is being specified
2) the "background.png" file exists in the same directory since it is not a web address and also does not have any directory traversal indication (example: ../background.png or /images/background.png)

So to access it, I will try appending it to the end of the url
`https://f9c3a15b61debe0bb887478cc573e908.ctf.hacker101.com/background.png`

And voila: 
![[Pasted image 20250513131333.png]]

## Lessons Learned:
KISS (Keep It Simple Stupid)