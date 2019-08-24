# Setup a Gatsby blog on Now with Markdown integration

In projects, run `$ npx gatsby-cli new my-gatsby-project`, and navigate into it  

`$ npm run build`  

To integrate markdown into the website, run  
`$ npm install --save gatsby-source-filesystem gatsby-transformer-remark`  

Once that's done:  
`$ touch gatsby-config.js`  

in `gatsby-config.js`:  

```
module.exports = {
  siteMetadata: {
    title: 'My Blog',
    description: 'This is my cool blog.'
  },
  plugins: [
    `gatsby-transformer-remark`,
    {
      resolve: `gatsby-source-filesystem`,
      options: {
        name: `pages`,
        path: `${__dirname}/src/pages`
      }
    }
  ]
}
```

**deploy with `$ now`**  