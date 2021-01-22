Welcome to the Secret Website Content Repository.

This Repository is a companion to the Secret Website Repository. Think of this as a sort of content management system or content database for the Secret Website.

Why is this seperated into a seperate repository?

There are a two reasons we made this choice:

#1 Seperation of Concerns: A traditional content based website like the Secret Network Website would have a content management system connected to a database. The CMS would be in charge the creating, updating and deleting from the database, while the site itself would read that content and render it to the vistor. The problem with this type of a system is overhead both in terms of management and cost. The Secret Website instead reads all data from Markdown files that each represent a page. By moving those files to a seperate repo, we are in essence, adding a content management system in the form of a github repository. Creating, updating and deleting are thus seperated from the website repo keeping the content management process in it's own world.

#2 Flexibility: With the seperation of concerns we gain flexibility that we didn't have before. We are able to use this repo as the single source of truth for multiple environments of the website itself. As a result we know that when we look at the development site, the content will be identical to production. If we want to we could create a content preview environment to view content changes ahead of release, or we could allow content to be updated in real time and fix errors through a crowdsource editing process. Both of these architectures, and many other, are possible now.

#3 Permissions: As we move forward we can be much more liberal with permissions allowing people to edit content without fear of effecting the core of the site architecture. We will be giving permissions to all commitee leads to start, but we expect that to expand as people more people show interest.

So now that I know the why, what about he how? How does one contribute to the content of the website?

Contributions can be made either in the github UI (Easy) or by forking the content repo and updating locally (Less Easy). Regardless of which you choose you will need to understand the structure of content repo.

Finding files:
Files names are mapped to routes on the site. Thuse if you want to add to the https://scrt.network/brand page, you would edit brand.md in the root directory. Files with subroots, e.g. https://scrt.network/ecosystem/overview is located in the ecosystem folder in the file overview.md

Getting comfortable with the format:
Although the files are .md files, they are not pure markdown. They contain references to components in the form of html tags. An example of this might look something like
```
<home-card to="/about/about-secret-network" vertical>
### **Learn about**<br>Secret Network
<separator small />
![Community](https://scrt.network/img/home-card/learn-about-secret-network.png)
</home-card>
```
This renders a "home card" component. In terms of "content" you have customized a component to say "Learn About Secret Network" and chosen and image to fill the card. The image is saved in the img/home-card folder. The look and feel of that content is determined by the component which exists in the core Secret Website Repo, in a file called HomeCard.vue in "src/components/home/HomeCard.vue"

Examples of components, and how they can be used, can be found on the contribute page of the site: htts://scrt.network/contribute

Adding good content:
Content can take the form of written or visual.

For written content we do not have a style guide, however we do recommend you look at the existing content and try to match the language as best as possible. A consistent voice is key to building and maintaining a reliable brand.

For visual content we do have a style guide. All style info can be found at https://scrt.network/brand. It is highly recommended that you download the BrandBook and look through it to get comfortable. You will also want look at the official Figma file https://www.figma.com/file/1MWJTRPRpoZUmIpzE4cMj2/Secret-Network-Website?node-id=270%3A0. This file is read-only, but any frame can be copied and worked on in a seperate file and then shared with the website commitee. If the changes require a component, you will need to do that in the core repo.

Process of Contributing
Directly on Github
Changes can be made directly to .md files by editing in github. Be sure to leave a good commit message so your changes are clear. When you submit changes, assuming you do not have commit privledges, you will be creating a pull request. Once you have done this, go to the Website room on discord and tell us that you submitted a pull request. We will review and if it looks good, merge. Once merged the development site will automatically update to reflect the changes. You can look at them and make any updates you need to match your intent. At regular intervals the live site will be manually rebuilt to reflect the content changes made.
