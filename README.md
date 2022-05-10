# fun-with-gpt3

A simple website for interacting with GPT-3, a natural language processing AI model. This site was created as part of my application to the 2022 Fall Front End Development Internship at Shopify. 

All the pertinent code can be found in src/components/HomePage.vue

You can see the site here: https://fun-with-gpt3-liam-gentile.netlify.app/

## Features
 - Prompt (a text input that the model continues off of)
 
 - Model Creativity Slider (a slider for model creativity - over to the right means more creative)
    - I chose to exclude telling the user specific values (real range is 0-1) for simplicity and a better UX experience 

## Accessibility

- Colour contrast: I made an effort to use sufficiently contrasting text and background 
- Semantic HTML: Where possible I used semantic HTML, i.e. button, label, textarea, input
- Clear Language: I avoided abbreviations, and described items explicitly. For example "drag to the right for more creativity", and "enter your prompt here"
- Verified that tab is working correctly. Tab from `url` to `text area` to `slider` to `submit` button.
## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```


