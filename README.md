# Website Code

The code uses Hugo to generate the static websites.
## Compile the code
- Clone this repo and the submodules
```bash
git clone --recurse-submodules https://github.com/vaishnavm217/website
```
- Install [hugo](https://gohugo.io)
- Run the following to run the server
```bash
hugo serve -D
```
- To generate the html files in `public` folder run
```bash
hugo
```

## Modify the website
```               
website
├───archetypes
├───content
│   └───blog
├───data
├───layouts
│   ├───blog
│   └───partials
├───resources
│   └───_gen
│       ├───assets
│       └───images
├───static
│   ├───css
│   ├───images
│   └───pdf               
```
- For basic editing like name and avatar, modify `config.toml`
- For adding new entries, run `hugo new <pagename>`
- For every section in `content`, there exist an layout in `layouts`.
- These are basic HTML files
- For modifying front page, edit index.html
- Make sure you don't edit themes files. If needed you can copy those files in the respective directory i.e `/themes/layout/index.html - > /layout/index.html` and then modify them.
