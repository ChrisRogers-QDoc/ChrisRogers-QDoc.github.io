# How to Host and Format your Resume on GitHub Pages

## Purpose  
The purpose of this README is to provide instruction on hosting your Markdown resume on GitHub Pages, and styling it with Jekyll. We will also tie in this process to the general principles written about in the book [Modern Technical Writing](https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS) by Andrew Etter.

## Prerequisites  
- [ ] A resume formatted in Markdown (must have the `.md` ([Markdown](https://www.markdownguide.org/getting-started/)) file type).
- [ ] An installation of [**Jekyll**](https://jekyllrb.com/docs/installation/), follow the instructions for the operating system you are using.
- [ ] An installation of [VS Code](https://code.visualstudio.com/) or similar code editor (Atom is another popular choice).
- [ ] A GitHub account.

## Instructions
### Creating our Jekyll Project
1. From your terminal (macOS/Linux) or your command prompt window, type `jekyll new myResume`, replacing `myResume` with whatever you would like to call your project. If you did everything correctly you should see something like the following:  
![image](https://user-images.githubusercontent.com/97467354/159175446-37432798-1334-4a76-95a1-a80f29855244.png)
2. Change directories into the newly created project directory by running `cd myResume`, again replacing `myResume` with whatever your project is actually called. In my case, it is `markdownResume`.
3. Lastly, run `bundle exec jekyll serve` and navigate to http://localhost:4000.  
**Note**: If the above command fails you may need to add `webrick` to your dependencies: `bundle add webrick`. Then repeat the above step.  


Your localhost should look like the following!
![image](https://user-images.githubusercontent.com/97467354/159176222-45932e0c-f8f4-41bc-bf14-52c57d2f41fc.png)

### Customizing your webpage locally
- If you are still running the Jekyll server, press `ctrl+c` in the terminal/command prompt it is running in to stop it.
- Open VS Code (or another suitable markdown editor like [Atom](https://atom.io/), and open the directory for the Jekyll project you have just created.
- In the file `index.markdown` in the root of the project copy and paste your markdown formatted resume *after* this block of code:  
![image](https://user-images.githubusercontent.com/97467354/159183929-35c12684-f4aa-4723-8767-86473efdfd04.png)

```
---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---
```
- Navigate to the file `_config.yml`, which is where we can customize the theme and metadata for the website.
  - Edit the `title` of your website, which is what will appear in the browser tab as well as the top of your website.
  - Edit the `email` value to an email address you wish to be reached at
  - Edit the `description` value, leaving the `>-`. It should look as follows:
  ```
  description: >- # this means to ignore newlines until "baseurl:"
  Chris Rogers' resume, hosted on GitHub Pages and styled using Jekyll for
  COMP 3040 at the University of Manitoba.
  ```
  - Edit your `github_username` and `twitter_username` if you wish to.
- You can delete the `_posts` folder from the project, as well as the file called `about.markdown`
- Run `

### Uploading to GitHub Pages
- Navigate and login to [GitHub](https://github.com/) and create a new repository by clicking on the green "New" button located on the left of your screen: ![image](https://user-images.githubusercontent.com/97467354/159386878-4fcb4042-23d0-4e06-86c7-f4d5ba0303d8.png)
- When prompted to name the repository, name it `{your github account name}.github.io`, as this is required by GitHub Pages.
- Optionally you can initialize the repository with a README.md, as well as providing a short description of what the repository is for. Leave everything else as default.

![Pasted image 20220321201036](https://user-images.githubusercontent.com/97467354/159388549-e372bbe8-7dea-4a12-9828-0f5a18d29218.png)

- Open your file explorer and locate the directory containing your Jekyll project.
- Click and drag the contents of the directory directly onto the GitHub repository page, which will copy the files from your computer to GitHub. These are the files you want to click and drag: ![image](https://user-images.githubusercontent.com/97467354/159388870-8270fac4-b0f6-4af5-9808-3e789928bf39.png)
- Your repository page should now look similar to this: ![image](https://user-images.githubusercontent.com/97467354/159388935-19dcc843-3a55-4916-a671-92f760e51944.png)
- Navigate to Settings -> Pages where you will now find a link stating that your project is now ready to be hosted on `https://{your github account}.github.io`, click that link to view your resume!

![Pages - Google Chrome 2022-03-21 20-27-25](https://user-images.githubusercontent.com/97467354/159389416-76935ebe-ac07-4787-b8c9-722949df65b2.gif)

## FAQ
**Why is Markdown better than a word processor?**
> Markdown is lightweight! This means that it doesn't require any difficult to read boilerplate in order to create beautiful static websites. Another benefit is that you don't need to purchase a subscription to use it, unlike Microsoft Word. Andrew Etter states in his book "Microsoft Word is a wonderful choice for creating resumes and a horrible choice for creating documentation. Its lone purpose... is to create short, attractive PDFs that can be consumed and discarded".

**Why is my resume not showing up?**
> This could be due to a couple of factors. First and foremost, make sure that your repository is correctly named. That means it needs to be called {your_github_username}.github.io, substituting your own GitHub username for the value in the brackets. For myself, that means my repository is called ChrisRogers-QDoc.github.io .
> Secondly, ensure that you've copied over all of the files from your Jekyll project, most importantly the `index.markdown` file which contains the content of your resume. If it didn't work on https://localhost:4000, it won't work on GitHub Pages.
> Lastly, sometimes GitHub Pages takes a while to update the website it is hosting! If you upload files, give the website a minute or two to catch up.




